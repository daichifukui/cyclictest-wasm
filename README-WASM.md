# Prerequisites

* Wasix-libc
  * Tested with HEAD 0374d06; may work with later versions
* Clang
  * Tested with version 16.0.0; may work with later versions
  * Target: wasm32-unknown-wasi
  * Thread model: posix
* Wasmer
  * Tested with version 4.1.1; may work with later versions

# How to build

```sh
$ make clean # optionally
$ make
```

# How to run

```sh
wasmer run --enable-all cyclictest -- -i 1000 --clock=1 -s --loops=10 --histogram=3000
```

You can change parameters for `loops` and `histogram`

# Caveats
* Interval cannot be shoter than 1000 us due to https://github.com/wasix-org/wasix-libc/issues/26
* Average is always zero on the screen
