---
layout: 'post'
title: 'what is a JavaScript JIT compiler'
date: '2016-12-04 11:25:00 +0800'
categories: JIT compiler
---

A browser consists of three JIT compilers, namely: JavaScript JIT compiler, CSS JIT compiler, and HTML JIT compiler.

So what is a JIT compiler in general? A JIT compiler runs *after* the program has started. It compiles the code (usually bytecode or some kind of VM instructions, for JavaScript JIT compiler, the code is JavaScript source code) just-in-time (on the fly) into a form that's usually faster. The form is typically the host CPU's native instruction set or bytecode for a Virtual Machine.

In contrast, a traditional compiler compiles all the code to machine language before the program is first run.

Considering a JavaScript JIT compiler, the responsibility of a JavaScript compiler is to convert high level JavaScript code into native computer instructions.

JavaScript Virtual Machine / engine consists of the JIT compiler part.

Another relevant term is JavaScript runtime. As to any runtime environment for a programming language, a JavaScript runtime provides runtime support when a JavaScript code is running via a virtual machine. For example, Node.js is a JavaScript runtime that is built on top of Google's V8 engine. It bridges the JavaScript world to the underlining operating system, providing features such as file system access.

The three articles below summarized 1) [the javascript engine family tree as of today.](http://creativejs.com/2013/06/the-race-for-speed-part-1-the-javascript-engine-family-tree/index.html)

2) [How they work in general?](http://creativejs.com/2013/06/the-race-for-speed-part-2-how-javascript-compilers-work/)

And 3) [the strategies that have been taken to make them faster](http://creativejs.com/2013/06/the-race-for-speed-part-3-javascript-compiler-strategies/index.html)
