real-time-cpp-toolchains
==================

This repository stores provides information and links to `Win*`-ported GNU/GCC toolchains
for building `ref_app` targets found in the repository
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).
These are needed when building the `ref_app` and examples on `Win*`.

## Supported Toolchain Targets

| GCC target             | location              |
| ---------------------- | --------------------- |
| `arm-none-eabi`        | [ARM(R) GNU Toolchain](https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads)  |
| `avr`                  | [ckormanyos/avr-gcc-build](https://github.com/ckormanyos/avr-gcc-build)                    |
| `rl78-unknown-elf`     | [ckormanyos/gcc-rl78-unknown-elf](https://github.com/ckormanyos/gcc-rl78-unknown-elf)      |
| `rx-elf`               | [ckormanyos/gcc-rx-elf](https://github.com/ckormanyos/gcc-rx-elf)                          |
| `v850-unknown-elf`     | [ckormanyos/gcc-v850-unknown-elf](https://github.com/ckormanyos/gcc-v850-unknown-elf)      |
| `x86_64-w64-mingw32`   | [nuwen distro](https://nuwen.net/mingw.html)                                               |
| `xtensa-esp32-elf`     | [espressif/crosstool-NG](https://github.com/espressif/crosstool-NG)                        |

## Further details

These GNU/GCC toolchains are built to run on Windows(R).
They can be used by developers who optionally run the builds in the
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp)
repository on `Win*` batches or in Microsoft(R) VisualStudio(R).

Other standalone uses are, of course, possible with these toolchains.
They are completely moveable and built to run out-of-the-box.

# Finding/Extracting the GNU/GCC Toolchains

Consult the links for the relevant toolchain(s) in the
[ref_app/tools/Util/msys64/usr/local](./ref_app/tools/Util/msys64/usr/local)
directory.

Consider, for instance, the `gcc-avr` toolchain.
It available in the release(s) of
[ckormanyos/avr-gcc-build](https://github.com/ckormanyos/avr-gcc-build).

The entire content of the relevant toolchain's directory are intended
to be moved or copied to the corresponding `ref_app` folder in
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).

# Using GNU/GCC Toolchains in the `ref_app` VS Solution

The GNU/GCC toolchains harmonize for use with the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository.
  - Clone (or get zip of) the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository, which is the main companion code for the book.
  - Consult the toolchain's notes in the [real-time-cpp-toolchains](https://github.com/ckormanyos/real-time-cpp-toolchains) repository, which is this repository.
  - Get the needed toolchain from its release or third-party location. Save it and extract its archive.
  - Move or copy the extracted toolchain to the corresponding location in the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository directory tree.
  - Open the `ref_app.sln` VisualStudio(R) solution as shown below.
  - Select the solution configuration and rebuild it. The results are placed in the temporary `ref_app/bin` directory

![](./images/real-time-cpp-target-avr-build.jpg)
