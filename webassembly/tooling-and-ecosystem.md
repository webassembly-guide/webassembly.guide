# Tooling & Ecosystem

The WebAssembly ecosystem is constantly growing. There are a lot of diverse tools that will help you enter the WebAssembly world with ease.

Here we will analyze the most popular ones:

### WebAssembly Studio

WebAssembly.Studio is an online IDE \(Integrated Development Environment\) that will help you learn and play with WebAssembly.

\(screenshot\)

### Visual Studio Code Extension

There is a great extension for Visual Studio Code that adds WebAssembly support into the IDE.

Including WebAssembly validation, and conversion to and from the binary and text format.

\(screenshot\)

Install the extension here:

[https://marketplace.visualstudio.com/items?itemName=dtsvet.vscode-wasm](https://marketplace.visualstudio.com/items?itemName=dtsvet.vscode-wasm)

### wabt

The WebAssembly Binary Toolkit. It's a collection of tools that let you manipulate WebAssembly files easily.

Here are their most popular ones:

* [**wat2wasm**](https://webassembly.github.io/wabt/doc/wat2wasm.1.html): translate from [WebAssembly text format](https://webassembly.github.io/spec/core/text/index.html) to the [WebAssembly binary format](https://webassembly.github.io/spec/core/binary/index.html)
* [**wasm2wat**](https://webassembly.github.io/wabt/doc/wasm2wat.1.html): the inverse of wat2wasm, translate from the binary format back to the text format \(also known as a .wat\)
* [**wasm-strip**](https://webassembly.github.io/wabt/doc/wasm-strip.1.html): remove sections of a WebAssembly binary file \(to optimize file size\)
* [**wasm-validate**](https://webassembly.github.io/wabt/doc/wasm-validate.1.html): validate a WebAssembly binary file

[https://github.com/WebAssembly/wabt](https://github.com/WebAssembly/wabt)

### Binaryen

Compiler infrastructure and toolchain library for WebAssembly.

Their most popular tool is:

* **wasm-opt**: Optimizes WebAssembly binaries to reduce file size or improve speed

### WAPM

The WebAssembly Package Manager. It's a centralized repository where developers and companies can install, publish and use WebAssembly packages.
