real-time-cpp-toolchains
==================

>ANNOUNCEMENT: This toolchain collection has been delegated to dedicated toolchain-specific repos.

# GNU/GCC Toolchains for [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) on Windows

This repository stores links to GNU/GCC toolchains needed
for building `ref_app` targets found in the repository
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).

## Supported Toolchain Targets

| GCC target             | location              |
| ---------------------- | --------------------- |
| `arm-none-eabi`        | [ARM(R) GNU Toolchain](https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads)  |
| `avr`                  | [ckormanyos/avr-gcc-build](https://github.com/ckormanyos/avr-gcc-build)                    |
| `rl78-unknown-elf`     | [ckormanyos/gcc-rl78-unknown-elf](https://github.com/ckormanyos/gcc-rl78-unknown-elf)      |
| `rx-elf`               | [this repo](./ref_app/tools/Util/msys64/usr/local)                                         |
| `v850-unknown-elf`     | [ckormanyos/gcc-v850-unknown-elf](https://github.com/ckormanyos/gcc-v850-unknown-elf)      |
| `x86_64-w64-mingw32`   | [nuwen distro](https://nuwen.net/mingw.html)                                               |
| `xtensa-esp32-elf`     | [espressif/crosstool-NG](https://github.com/espressif/crosstool-NG)                        |

## Further details

These GNU/GCC toolchains are built to run on Windows(R).
They are intended to be used by developers who optionally
run the builds in the
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp)
repository on `Win*` batches or in Microsoft(R) VisualStudio(R).

Other standalone uses are, of course, possible with these toolchains.
They are completely moveable and built to run out-of-the-box.

## Build details

All GCC builds (including binutils and prerequisites) have been performed
on [mingw64/msys2](https://www.msys2.org) with `--host=x86_64-w64-mingw32`.

# Finding/Extracting the GNU/GCC Toolchains

See the notes/links for the relevant toolchain(s) in the
[ref_app/tools/Util/msys64/usr/local](./ref_app/tools/Util/msys64/usr/local)
directory.

Consider, for instance, the `gcc-avr` toolchain.
It available in the release(s) of
[ckormanyos/avr-gcc-build](https://github.com/ckormanyos/avr-gcc-build).

Upon obtaining the toolchain,
the entire contents of of the `tools` directory are intended
to be moved or copied to the corresponding `ref_app` folder in
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).

# Using GNU/GCC Toolchains in the `ref_app` VS Solution

The GNU/GCC toolchains harmonize for use with the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository.
  - Clone (or get zip of) the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository, which is the main companion code for the book.
  - Clone (or get zip of) the [real-time-cpp-toolchains](https://github.com/ckormanyos/real-time-cpp-toolchains) repository, which is this repository.
  - Get the needed toolchain, save it and extract its archive.
  - Move or copy the extracted toolchain to the corresponding location in the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository directory tree.
  - Open the `ref_app.sln` VisualStudio(R) solution as shown below.
  - Select the solution configuration `target avr` and rebuild it. The results are placed in the temporary `ref_app/bin` directory

![](./images/real-time-cpp-target-avr-build.jpg)
