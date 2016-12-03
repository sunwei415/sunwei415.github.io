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