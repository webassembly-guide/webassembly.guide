# Security

WebAssembly is designed to be completely sandboxed. This is of critical importance for assuring maximum security of webpages. We would never like to visit a website and allow them to steal information from us. The same way that websites are sandboxed and safe, so should be WebAssembly.

### Why?

These are the main reasons WebAssembly is secure:

* Memory safety: WebAssembly programs have a linear memory that can't be accessed outside of its bounds.
* Undefined behavior: is impossible thanks to the semantics of WebAssembly
* Code injection: is literally impossible. All the functions used will needed to be declared at load time, and no functions can be generated at runtime \(this also makes impossible having JITs in pure Wasm\)
* Host functions: By default WebAssembly have no access to the host

Of all this properties, the host functions could be the most sensitive, but also the ones that can give us more control over the things that our WebAssembly program is able to execute.

**Which of these statements is true?**

* WebAssembly is as secure as Internet Explorer with ActiveX
* WebAssembly is designed to be safe and sandboxed
* We can have JITs compiled into WebAssembly
* A Host function can't be insecure

