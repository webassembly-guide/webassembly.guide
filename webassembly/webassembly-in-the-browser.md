# WebAssembly in the Browser

All major browsers \(Google Chrome, Safari, Edge, Firefox and Opera\) now support WebAssembly.  
As of November 2019 WebAssembly also become a W3C recommendation.

By using WebAssembly on the browser, we can:

* Increase the speed of our Javascript applications, removing bottlenecks on CPU-intensive computations
* Use more programming languages in our web apps \(other than JS\)

## Why is WebAssembly faster than JavaScript?

Over the years the browsers have been competing to improve the speed of JavaScript programs in the browser. That lead to state of the art JS runtimes, such as:

* V8 \(Google Chrome\)
* JavascriptCore \(Safari\)
* SpiderMonkey \(Firefox\)

However, when running a simple JS program, the Javascript VMs need to do a lot of checks to conform to the JS specification. On the other side, Wasm programs are compiled and optimized ahead of time.

In that sense, the WebAssembly specification is much more low-level than JS. That means that it's easier to translate its bytecode to something the machine can run \(with fewer checks\), leading to much faster speeds.

Example of this speed improvements are:

* Tensorflow: it achieved 2x speed

## More programming languages in the Browser

Thanks to the adoption of WebAssembly, more programming languages have been trying to compile into WebAssembly as a way to increase their adoption and use.

One great example of this is Rust. They embraced WebAssembly as a first-class citizen in their ecosystem and that increased their adoption allowing Rust programs to be usable in the Browser.

However, there are many more programing languages that can be run in the Browser:

* C/C++: via [Emscripten](https://emscripten.org/) or [Wasienv](https://github.com/wasienv/wasienv)
* Rust: [natively](https://www.rust-lang.org/what/wasm)
* Go: [natively](https://github.com/golang/go/wiki/WebAssembly)
* Java: with transpilers like [TeaVM](http://teavm.org/)
* .Net / C\#: via [Blazor](https://dotnet.microsoft.com/apps/aspnet/web-apps/blazor)

## Who is using WebAssembly in the browser?

There are tons of companies using WebAssembly in the browser. Some of those are:

* Figma
* AutoCAD
* Qt
* Pyodide
* Squoosh
* 
**Which of these statements is true?**

* WebAssembly can run in all browsers
* WebAssembly is not yet a W3C recommendation
* Only Rust can compile to WebAssembly
* There are no companies using WebAssembly

