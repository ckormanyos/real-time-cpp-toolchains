real-time-cpp-toolchains
==================

>ANNOUNCEMENT: This toolchain collection currently being distributed to specific, dedicated repos.

# GNU/GCC Toolchains for [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) on Windows

This repository stores GNU/GCC toolchains needed
for building `ref_app` targets found in the repository
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).

## If you just want the toolchains

If you simply want to get any/all of the GNU/GCC toolchains for your own use, they can be found
either as linked alternate locations or as multi-file, self-extracting archives
in the [ref_app/tools/Util/msys64/usr/local](./ref_app/tools/Util/msys64/usr/local) directory.

## Further details

These GNU/GCC toolchains are built to run on Windows(R).
They are intended to be used by developers who optionally
run the builds in the
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp)
repository on `Win*` batches or in Microsoft(R) VisualStudio(R).

Other standalone uses are, of course, possible with these toolchains.
They are completely moveable and built to run out-of-the-box.

## Supported Toolchain Targets

| GCC target             | GCC version   | location              |
| ---------------------- | ------------- | --------------------- |
| `arm-none-eabi`        | 13.2.1        | [ARM(R) GNU Toolchain](https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads)  |
| `avr`                  | 13.2.0        | [ckormanyos/avr-gcc-build](https://github.com/ckormanyos/avr-gcc-build)                    |
| `rl78-unknown-elf`     | 11.2.0        | [this repo](./ref_app/tools/Util/msys64/usr/local)                                         |
| `rx-elf`               | 11.2.0        | [this repo](./ref_app/tools/Util/msys64/usr/local)                                         |
| `v850-unknown-elf`     | 13.2.0        | [ckormanyos/avr-gcc-build](https://github.com/ckormanyos/avr-gcc-build)                    |
| `x86_64-w64-mingw32`   | 13.2.0        | [nuwen distro](https://nuwen.net/mingw.html)                                               |
| `xtensa-esp32-elf`     | 13.2.0        | [espressif/crosstool-NG](https://github.com/espressif/crosstool-NG)                        |


## Build details

All GCC builds (including binutils and prerequisites) have been performed
on [mingw64/msys2](https://www.msys2.org) with `--host=x86_64-w64-mingw32`.

# Finding/Extracting the GNU/GCC Toolchains

GNU/GCC toolchains are stored as self-extracting archives in the
[ref_app/tools/Util/msys64/usr/local](./ref_app/tools/Util/msys64/usr/local)
directory.

The JPG image below
depicts the topology of the GNU/GCC toolchains in the
[real-time-cpp-toolchains](https://github.com/ckormanyos/real-time-cpp-toolchains)
repository and how these topologically harmonize with the `ref_app`
in the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository.

![JPG image](./images/real-time-cpp-toolchains.jpg)

Consider, for instance, the `gcc-avr` toolchain version 11.2.0.
It is stored in the executable file `gcc-11.2.0-avr.exe`.
This file has been split into several self-extracting
archives in order to limit individual file storage to 64MB.

This file (and its affiliated sub-archives) can be extracted,
for example, via double click or suitable command
on the command line (cmd).

For instance, extract `gcc-11.2.0-arv.exe` in `Win*` with the command:

```cmd
start /b /wait ./gcc-11.2.0-avr.exe -y -gm2 -InstallPath=".\\gcc-11.2.0-avr"
```

Upon extraction of one or more of the toolchains,
the entire contents of of the `tools` directory are intended
to be moved or copied to the `ref_app` folder in
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).

The `tools` directory (after extracting the self-extracting GNU/GCC archives)
is intended to be copied or dragged-and-dropped to within the `ref_app`
directory of [real-time-cpp](https://github.com/ckormanyos/real-time-cpp).
This creates the directory `ref_app\tools` which subsequently
enables the MSVC GNU/GCC target builds to work out-of-the-box in `ref_app.sln`,
when opened in Microsoft(R) VisualStudio(R).

# Using GNU/GCC Toolchains in the `ref_app` VS Solution

The GNU/GCC toolchains harmonize for use with the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository.
  - Clone (or get zip of) the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository, which is the main companion code for the book.
  - Clone (or get zip of) the [real-time-cpp-toolchains](https://github.com/ckormanyos/real-time-cpp-toolchains) repository, which is this repository.
  - Step 1. Extract one or more of the GNU/GCC toolchains in [ref_app/tools/Util/msys64/usr/local](./ref_app/tools/Util/msys64/usr/local) directory. The executable files are self-extracting archives that extract in-place where they are intended to be, such as via double-click.
  - Step 2. Following toolchain extraction(s), move or copy the [ref_app/tools](./ref_app/tools) directory from `real-time-cpp-toolchains` (this repository) to the corresponding location in the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository directory tree.
  - Open the `ref_app.sln` VisualStudio(R) solution as shown below.
  - Select the solution configuration `target avr` and rebuild it. The results are placed in the temporary `ref_app/bin` directory

![](./images/real-time-cpp-target-avr-build.jpg)

# Building a GCC Cross Toolchain on msys2/mingw64

## Notes

Full notes and instructionis on building various GCC cross toolchains
on `msys2`/`mingw64` are provided in the [notes](./notes) directory.
