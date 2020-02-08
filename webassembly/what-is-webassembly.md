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



{% embed url="https://www.youtube.com/watch?v=fvkIQfRZ-Y0" %}

## Adoption

Since the WebAssembly Minimum Viable Product \(MVP\) for the binary format was reached, WebAssembly has been increasing it's popularity allowing companies and developers run programs at incredible speeds in the browser.

Also, a new trend emerged by leveraging on the speed, safety and portability of WebAssembly server-side \(outside of the browser\).

Companies like [CloudFlare](https://www.cloudflare.com/), [Fastly](https://www.fastly.com/) and [Wasmer](https://wasmer.io/) created their own standalone WebAssembly runtimes to run Wasm server-side \(think of what Node.js did to run JavaScript server-side, but for WebAssembly\).

## Format

WebAssembly code \(the code that express a program\) can be expressed in two ways:

* Binary
* Text

#### WebAssembly Binary Format

The binary format is designed to be:

* Small: so the WebAssembly program size is as small as possible
* Easy to extend: so as WebAssembly evolves it minimizes the breaking changes
* Fast to parse: so the runtimes do minimal effort reading the bytecode

Here's an example of a WebAssembly binary file:

{% tabs %}
{% tab title="add.wasm \(binary format\)" %}
```scheme
0061 736d                                 ; WASM_BINARY_MAGIC
0100 0000                                 ; WASM_BINARY_VERSION
01                                        ; section code
00                                        ; section size
01                                        ; num types
60                                        ; func
02                                        ; num params
7f                                        ; i32
7f                                        ; i32
01                                        ; num results
7f                                        ; i32
07                                        ; FIXUP section size
03                                        ; section code
00                                        ; section size (guess)
01                                        ; num functions
00                                        ; function 0 signature index
02                                        ; FIXUP section size
07                                        ; section code
00                                        ; section size (guess)
01                                        ; num exports
03                                        ; string length
6164 64                                   ; export name "add"
00                                        ; export kind
00                                        ; export func index
07                                        ; FIXUP section size
0a                                        ; section code
00                                        ; section size
01                                        ; num functions
00                                        ; func body size
00                                        ; local decl count
20                                        ; local.get
00                                        ; local index
20                                        ; local.get
01                                        ; local index
6a                                        ; i32.add
0b                                        ; end
07                                        ; FIXUP func body size
09                                        ; FIXUP section size
```
{% endtab %}
{% endtabs %}

As you can see, the binary file is not easily readable by humans.

{% hint style="info" %}
You can find more info in the normative documentation for the binary format specification: [https://webassembly.github.io/spec/core/binary/index.html](https://webassembly.github.io/spec/core/binary/index.html)
{% endhint %}

#### WebAssembly Text Format

Because of that, the WebAssembly core team also created a text format translatable to the binary format.

Here's a snippet of the previous WebAssembly program in it's text representation:

{% tabs %}
{% tab title="add.wat \(text format\)" %}
```haskell
(module
  (func $add (param $lhs i32) (param $rhs i32) (result i32)
    local.get $lhs
    local.get $rhs
    i32.add)
  (export "add" (func $add))
)
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
You can find more info in the normative documentation for the WebAssembly text format specification: [https://webassembly.github.io/spec/core/text/index.html](https://webassembly.github.io/spec/core/text/index.html)
{% endhint %}

## **Which of these statements is true?**

* WebAssembly was invented by Google
* WebAssembly is an industry adopted standard
* WebAssembly can only run inside the browser
* WebAssembly has only a binary format

