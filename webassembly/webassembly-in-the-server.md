# WebAssembly in the Server

Even though WebAssembly was initially designed to run in the browser, it's usage on the server-side is reaching wider adoption. Mainly because WebAssembly first principles:

* It's fast and lightweight
* It's portable: it can run in any platform & architecture
* It's sandboxed

These properties make WebAssembly as the ideal contender to run untrusted code, safely and fast anywhere, specially outside of the browser.

Here are some of the use cases for using WebAssembly server-side:

* Universal programs
* Edge Computing & IoT
* Universal libraries / Plugins
* Blockchain & Decentralized Platforms
* Serverless

## Universal Programs

Previously, programs could only be run in a specific platform and architecture. For example, Windows programs couldn't run on Mac \(different platform\), or Mobile programs can't run in Desktop \(different architecture\).

The main reason why is was technical: the program binary was only executable in the platform and architecture was created on.

However, there were other solutions like the JVM or OS-based containers \(such as Docker\) that opened the possibility to run a single bytecode file universally.

However, this two approaches are not as good as WebAssembly for universal programs. Here's why:

* The JVM is a very solid, but heavy VM. Just the JVM VM and framework is around 200Mb. Apart fromt his, its bytecode format is not as low level as Wasm.
* Docker is an OS-based container. That means that it has an entire OS in the container in order to be able to run your program. This makes Docker containers both slow on initialization and heavy on size compared to WebAssembly programs. At the same time, Docker containers are platform agnostic, but chipset dependent.

## Edge Computing & IoT

Cloud Computing was the first trend that allowed applications and companies to scale easily without worrying about physical servers. However, once most of the companies embraced this trend, the computing power became more centralized into fewer hands \(namely Amazon Web Services, Microsoft Azure and Google Cloud\).

Thanks to new trends like 5G, we have now the opportunity to run software in places that were impossible before \(routers, IoT devices...\), which leads into a more decentralized ecosystem.

Because of that, WebAssembly is the perfect contender for Edge Computing as it allows running software on this places in a light, universal and safe way.

## Universal Libraries / Plugins

If you want to use C/C++ libraries in other languages \(eg. JS or Python ecosystem, for example\) it get's very challenging. The main reason on why, is because you have to write all the bindings between the language the plugin was written in \(usually C/C++ or Rust\) and the host language \(JS or Python\).

Once you do that

Because of that, WebAssembly is the ideal format for libraries that are meant to be used across any language.

## Blockchain & Decentralized Platforms

Bitcoin was the first platform that popularized decentralized trust on the storage level \(blockchain\).

After blockchain became mainstream, new platforms like Ethereum introduced a way to not only have decentralized trust on storage \(blockchain\), but also execution \(Smart Contracts, as a way to run logic each time a transaction happened\).

Ethereum created their own VM \(EVM\) to run this Smart Contracts, along with new languages \(Solidity, Vyper\) inspired by popular ones \(JavaScript, Python respectively\) to allow ease of use of this contracts for developers.

However, over time, the Smart Contract developers realized that there were some issues with the EVM approach:

* They could not reuse programs that already existed in other languages
* The EVM machine was not as optimal/fast as they would have liked

Because of that, there is a push from decentralized platforms to move from the EVM model into a new architecture based on WebAssembly: [ewasm](https://github.com/ewasm/design).

This have a lot of nice implications:

* They can create Smart Contracts in languages that compile into WebAssembly, thus reuse code and knowledge on already-existing programming languages
* The Smart Contracts will run optimally, safe and universally anywhere

**Which of these statements is true?**

* WebAssembly is a heavy
* WebAssembly programs are fast, portable and sandboxed
* EVM programs are faster
* WebAssembly has only a binary format

