# Emscripten Tutorial

{% hint style="info" %}
Note: The final project for this tutorial can be found on GitHub. You can always use it as a reference whenever you get lost throughout the course of the following chapters. Also note that each code block is annotated with a filename. These annotations directly link to the corresponding file on GitHub, so you can clearly see where to put the code and what the end result will look like
{% endhint %}

**Need some help?** No tutorial is perfect and questions always come up, so [feel free to reach out to us and the community over on the Wasmer Spectrum](https://spectrum.chat/urql), if you have any questions or need some help!

## **Overview**

In the previous tutorials, you learned about major concepts and benefits of WebAssembly. Now is the time to get your hands dirty and start out with an actual project!

You’re going to build a simple WebAssembly module that does some heavy computation.

In this track, you’ll use the following technologies for building the app:

* C/C++
* Emscripten
* JavaScript

### Emscripten vs WASI

[Emscripten](https://emscripten.org/) is a great toolchain that let's you compile your C/C++ projects to WebAssembly so you can use them in the web easily.

However, Emscripten has a **non-stable ABI** \(because constant and fast iteration is very useful for their usecase\). This makes it a bit challening for standalone-runtimes to continually adapt. Because of that, adopting the WASI ABI is a much easier path for standalone server-side WebAssembly runtimes.

WASI is also designed to have a sandboxed filesystem. However, since our filesystem will be mainly emulated in the web both WASI and Emscripten are great choices for it.

Since on this tutorial we will be focusing on Web only, Emscripten should be a great choice because their focus on minimal glue code size between JS and WebAssembly.

