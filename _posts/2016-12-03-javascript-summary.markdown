---
layout: 'post'
title: 'JavaScript Summary'
date: '2016-12-03 12:54:00 +0800'
categories: JavaScript Why tip
---

1. implicit global variable creation:
{% highlight javascript %}
    {aName = 'ExplainThat!';}
    {% endhighlight%}
    // If variable aName is never defined before, the JavaScript runtime will create one in the global scope. But why it is created/defined in the global scope? The easy answer is that the JavaScript language is designed to behave like this. My understanding is that, during variable name resolving process during javascript code execution, the runtime is trying to find aName according to the scope chain attached to the current execution context, but it ends in the global scope and failed, thus the easiest and possibly fastest way is to create one at the scope where the resolving process ends,  i.e., the global scope. This breaks the general modularization principle in software design. Is the 'use strict' statement introduced in es5 helpful in this case?

1. JavaScript code execution
    code execution happens in two phases: the compilation phase and the execution phase.
    compilation phase: input: source code
    output: variable table for the current scope
    process: only var, function is collected as variables
    variable declaration with assignment, the assignment is not executed
    execution phase: input: source code + variable table
    output: code execution
    process: use prototype chain for object property resolving
    use scope chain for variable resolving
    callback queue
    render queue
    callstack
    web api execution

    responsibility of JavaScript runtime
    who provides event loop
1. JavaScript engine vs. JavaScript runtime
    an engine is responsible for providing the mechanics of parsing and JIT compilation, i.e., producing machine-executable operations from a script written in JavaScript.
    The runtime provides the built-in libraries that are available to the program at runtime (during execution).
    The runtime is to the engine in a way that the linker is to the compiler in a traditional compiled language.
    
1. Internal APIs
    1. encodeURI: encodes everything except :/?&;,~@&=$+=_.*()# and alphanumerics
    we can use encodeURI to get legal URI string. This is due to the fact a). whitespace not allowed in URI b). URI should be ASC-II encoded. Thus we need to encode non-ASC-II characters and whitespaces via percent encoding. E.g., whitespace is encoded as %20.
    1. encodeURIComponent: encodes everything except _.-!~*() and alphanumerics
    we can use encodeURIComponent to get legal url parameter values. For example, in url: http://me.com?key=value, if value contains = character, this can need to url parameter injection. Also the ASC-II nature of URI requires the value to be encoded.
    
1. xor ^ operator: a ^ b when aligning the bits for a and b, for each bit position, if they are the same for a and b, the resulting bit will be 1, otherwise it is zero.
1. typeof funcA == 'function'
1. typeof [] == 'object'
1. we can use isFinite to tell if an variable is Infinity or not
1. var a = null ? true: false --> a = false;
1. null == false --> false
1. in Node.js: use global['aName'] to tell if variable aName exists in global scope.
1. [].prototype == undefined


