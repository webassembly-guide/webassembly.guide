# What is WebAssembly?

WebAssembly is an [open standard](https://webassembly.org/) that defines a portable binary code format for executable programs, and a corresponding textual assembly language, as well as interfaces for facilitating interactions between such programs and their host environment.

WebAssembly let us run a wider range of programming languages in the browser \(such as Rust, C, C++, ...\) and also outside of the browser in a universal, portable and safe way.

WebAssembly is designed to be:

* Portable
* Fast
* Sandboxed

## History & Context

WebAssembly was created by browser vendors with the main goal of achieving near-native speed when running applications on the browser, as the JavaScript runtimes even though they are super fast, can't achieve near-native speeds.

There are two main sources that the WebAssembly standard took inspiration from: [asm.js](http://asmjs.org/) and [PNaCl](https://developer.chrome.com/native-client).

#### asm.js

asm.js was a subset of JS designed to include "typing" into the JavaScript code, so the JS runtimes in the browsers could easily optimize them into optimal machine code.

asm.js was mainly used by [Emscripten](https://emscripten.org/), a source-to-source translator that translated LLVM bitcode into JS code.

As almost all C/C++ programs could be easily translated into LLVM bitcode, that helped to make tons of C/C++ available in the browser, and helped to increase the popularity of what eventually become WebAssembly.

#### PNaCl

On the other side, Google developed NaCl \(Native Client\) and PNaCl \(Portable Native Client - pronounced "pinacle"\).

PNaCl was a great technical advance, but it only got support from one vendor: Google. The other browser vendors rejected the idea stating things like "These native apps are just little black boxes in a webpage. \[...\] We really believe in HTML, and this is where we want to focus.".

WebAssembly, however took the learnings from both PNaCl and asm.js and emerged as a new standard now adopted by all industry \(Google, Mozilla and Apple\).

### Video: What is WebAssembly?

[https://www.youtube.com/watch?v=fvkIQfRZ-Y0](https://www.youtube.com/watch?v=fvkIQfRZ-Y0)

## Adoption

Since the WebAssembly Minimum Viable Product \(MVP\) for the binary format was reached, WebAssembly has been increasing it's popularity allowing companies and developers run programs at incredible speeds in the browser

Also, a new trend emerged by leveraging on the speed, safety and portability of WebAssembly as a way to run programs server-side \(outside of the browser\).

Companies like CloudFlare, Fastly and Wasmer created their own standalone WebAssembly runtimes \(think of what Node.js did to run JavaScript server-side, but for WebAssembly\).

## Format

WebAssembly bytecode \(the code that express a program\) can be represented in two ways:

* Binary
* Text

The binary format is designed to be:

* Small: so the WebAssembly program size is as small as possible
* Easy to extend: so as WebAssembly evolves it minimizes the breaking changes
* Fast to parse: so the WebAssembly runtimes do minimal effort when processing WebAssembly bytecode

Here's the normative documentation for the binary format specification: [https://webassembly.github.io/spec/core/binary/index.html](https://webassembly.github.io/spec/core/binary/index.html)

Here's an example of a WebAssembly binary bytecode:

As you can see, the binary text is not readable by humans \(at least easily\).

Because of that, the WebAssembly core team also created a text format translatable to the binary format:

```text
# Example text format
```

Here's the normative documentation for the WebAssembly text format specification: [https://webassembly.github.io/spec/core/text/index.html](https://webassembly.github.io/spec/core/text/index.html)

## **Which of these statements is true?**

* WebAssembly was invented by Google
* WebAssembly is an industry adopted standard
* WebAssembly can only run inside the browser
* WebAssembly has only a binary format

