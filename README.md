# hello emscripten

**You:**

explain webassembly

---

**ChatGPT:**

WebAssembly (often abbreviated as Wasm) is a binary instruction format that serves as a low-level compilation target for programming languages. It is designed to enable efficient execution of code on the web and other platforms. WebAssembly is supported by all major web browsers, allowing developers to run high-performance applications in web environments.

Here are some key points about WebAssembly:

Language Agnostic: WebAssembly is language agnostic, meaning it can be generated from various programming languages such as C, C++, Rust, and more. It provides a standardized format for executing code across different platforms.

Binary Format: WebAssembly code is represented in a compact binary format that is designed to be fast to decode and execute. It is not meant to be written or read by humans directly, but rather generated by compilers or other tools.

Virtual Machine: WebAssembly introduces a virtual machine that is implemented by web browsers. This virtual machine executes the WebAssembly binary code efficiently, providing near-native performance.

Portability: WebAssembly is designed to be highly portable. It can run not only on web browsers but also on other platforms such as servers, IoT devices, and embedded systems. It aims to bridge the gap between the web and other computing environments.

Performance: WebAssembly is designed for high-performance execution. By utilizing a low-level bytecode representation, it can achieve near-native execution speeds. This makes it suitable for computationally intensive tasks, games, multimedia applications, and more.

Security: WebAssembly runs inside a sandboxed environment provided by web browsers. This sandboxing ensures that WebAssembly code cannot access or modify sensitive resources on the user's device without explicit permissions. It provides an additional layer of security for executing code from untrusted sources.

Integration with JavaScript: WebAssembly is designed to work alongside JavaScript. It provides a seamless integration mechanism, allowing JavaScript code to interact with WebAssembly modules. This interoperability enables developers to leverage existing JavaScript libraries and frameworks within WebAssembly projects.

WebAssembly has gained popularity due to its ability to bring high-performance and efficient code execution to the web. It allows developers to bring existing codebases, written in different languages, to the web without significant modifications. With its broad support across browsers, WebAssembly is poised to enable a new generation of web applications with improved performance and functionality.

---

**You:**

a hello world example?

---

**ChatGPT:**

Certainly! Here's a simple "Hello, World!" example using WebAssembly:

First, let's create a C source file named hello.c:

```
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

Next, let's compile the C code into WebAssembly using a C compiler that supports WebAssembly. For example, you can use Emscripten, a popular tool for compiling C/C++ to WebAssembly. Assuming you have Emscripten installed, run the following command in your terminal:

```
emcc hello.c -o hello.html
```

This command will generate an hello.html file along with the WebAssembly module (hello.wasm) and the JavaScript glue code.

Finally, open the hello.html file in a web browser, and you should see the "Hello, World!" message printed in the browser's console.

That's it! You've successfully executed a "Hello, World!" program using WebAssembly.

---

```
 brew install emscripten
 ...
```

---

```
hello-emscripten % emcc hello.c -o hello.html
emcc: warning: config file not found: /usr/local/Cellar/emscripten/3.1.41/libexec/.emscripten.  You can create one by hand or run `emcc --generate-config`
emcc: error: BINARYEN_ROOT not set in config (/usr/local/Cellar/emscripten/3.1.41/libexec/.emscripten), and `wasm-opt` not found in PATH
```

---

```
hello-emscripten % emcc --generate-config
emcc: error: config file already exists: `/usr/local/Cellar/emscripten/3.1.41/libexec/.emscripten`
```

---

```
hello-emscripten % emcc hello.c -o hello.html
shared:INFO: (Emscripten: Running sanity checks)
cache:INFO: generating system headers: sysroot_install.stamp... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot_install.stamp" for subsequent builds)
cache:INFO:  - ok
cache:INFO: generating system asset: symbol_lists/388ef6fbf0a94e44c596dda168ce9a7e9891a61b.json... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/symbol_lists/388ef6fbf0a94e44c596dda168ce9a7e9891a61b.json" for subsequent builds)
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libGL.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libGL.a" for subsequent builds)
system_libs:INFO: compiled 3 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libal.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libal.a" for subsequent builds)
system_libs:INFO: compiled 1 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libhtml5.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libhtml5.a" for subsequent builds)
system_libs:INFO: compiled 2 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libstubs-debug.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libstubs-debug.a" for subsequent builds)
system_libs:INFO: compiled 2 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libnoexit.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libnoexit.a" for subsequent builds)
system_libs:INFO: compiled 1 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libc-debug.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libc-debug.a" for subsequent builds)
system_libs:INFO: compiled 1023 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libdlmalloc.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libdlmalloc.a" for subsequent builds)
system_libs:INFO: compiled 1 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libcompiler_rt.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libcompiler_rt.a" for subsequent builds)
system_libs:INFO: compiled 175 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libc++-noexcept.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libc++-noexcept.a" for subsequent builds)
system_libs:INFO: compiled 49 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libc++abi-debug-noexcept.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libc++abi-debug-noexcept.a" for subsequent builds)
system_libs:INFO: compiled 16 inputs
cache:INFO:  - ok
cache:INFO: generating system library: sysroot/lib/wasm32-emscripten/libsockets.a... (this will be cached in "/usr/local/Cellar/emscripten/3.1.41/libexec/cache/sysroot/lib/wasm32-emscripten/libsockets.a" for subsequent builds)
system_libs:INFO: compiled 21 inputs
cache:INFO:  - ok
hello-emscripten % ll
total 376
-rw-r--r--  1 rudifarkas  staff   4.0K Jun 21 12:10 README.md
-rw-r--r--  1 rudifarkas  staff    80B Jun 21 12:07 hello.c
-rw-r--r--@ 1 rudifarkas  staff   100K Jun 21 12:18 hello.html
-rw-r--r--@ 1 rudifarkas  staff    58K Jun 21 12:18 hello.js
-rwxr-xr-x@ 1 rudifarkas  staff    12K Jun 21 12:18 hello.wasm
```
