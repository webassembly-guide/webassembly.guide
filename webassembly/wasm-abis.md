# Wasm ABIs



An application binary interface \(ABI\) is an interface between two binary program modules.\  
In the WebAssembly case, we refer to ABI as the way the Modules are going to interact with the host system.

### _But... why the modules would like to interact with the host system?_

Sometimes we would like the Modules to have capabilities that only the OS can fulfill, outside of pure compute power. For example, when trying to get the contents of a file, or when creating a socket to create a webserver.

To date, these are the most popular ABIs for WebAssembly:

* Emscripten
* WASI
* GoJS

## Emscripten

Emscripten was the first project to define a POSIX-complaint ABI. Most of the programs that we execute in Linux, MacOS or Unix Environments are using the POSIX ABI.

That way, any POSIX program made in C or C++ could be executed in the browser via WebAssembly.

Emscripten has a few advantages and disadvantages:

* It's ideal for browser usage, since it optimizes for code size
* The ABI Is not stable \(can change in between versions\)
* Is not designed to be completely sandboxed when running outside of the Browser

## WASI

WASI is a WebAssembly ABI inspired by CloudABI that allows doing system calls in a permission based fashion. That way, the WebAssembly modules would only have the access that we allow them to do.

WASI is not designed POSIX compliant. This means that not all the POSIX programs that we can run in Linux/Mac would be able to compile or run in WebAssembly.

Right now, WASI is adopted in Rust and can be also easily used from C and C++ projects \(via Wasienv or using the WASI-SDK directly\).

## GoJS

Go defines it's own ABI when compiling go programs to WebAssembly.

This ABI is designed to be flexible with any JS environment \(browsers or Node.js\), but it makes harder to use standalone in server-side, as standalone WebAssembly runtimes doesn't run with in a JS VM.

**Which of these statements is true?**

* An ABI is an interface that allow Modules to interact with the host OS
* We will never be able to open sockets with WebAssembly
* Emscripten is designed to be sandboxed
* WASI is POSIX complaint

