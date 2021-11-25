# GNU/GCC Toolchains for real-time-cpp on Windows

This repository is intended to store GNU/GCC toolchains needed
for building `ref_app` targets for the repository
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).
These GNU/GCC toolchains are built to run on Windows(R).

## Supported toolchain targets

| GCC target arch (as used in configure) | Version       | C-Library     | bfd             |
| -------------------------------------- | ------------- | ------------- | --------------- |
| `avr-gcc`                              | 11.2.0        | avr-libc3     | binutils 2.37   |
| `arm-none-eabi-elf-gcc`                | 11.2.0 (TBD)  | newlib 4.1.0  | binutils 2.37   |
| `rl78-unknown-elf-gcc`                 | 11.2.0        | newlib 4.1.0  | binutils 2.37   |
| `rx-elf-gcc`                           | 11.2.0 (TBD)  | newlib 4.1.0  | binutils 2.37   |
| `v850-unknown-elf-gcc`                 | 11.2.0 (TBD)  | newlib 4.1.0  | binutils 2.37   |

## Build details

All builds performed on [mingw64/msys2](https://www.msys2.org)
with `--host=x86_64-x64-mingw32` with preference for static linking.

The following packages and prerequisites have been used.
Each package and prerequisite has been built on `--host=x86_64-x64-mingw32`
with static linkage.
  - libiconv 1.16 (package)
  - GMP 6.2.1 (prerequisite)
  - MPFR 4.1 (prerequisite)
  - MPC 1.2.1 (prerequisite)
  - ISL 0.15 (prerequisite)
  - cloog 0.18.1 (package)

### Configurations

The build of `rl78-unknown-elf-gcc` has been configured with:

```
../gcc-11.2.0_with_newlib-4.1.0/configure --prefix=/usr/local/gcc-11.2.0-rl78-unknown-elf --target=rl78-unknown-elf --enable-languages=c,c++ --build=x86_64-w64-mingw32 --host=x86_64-w64-mingw32 --with-pkgversion='ckormanyos/real-time-cpp' --enable-static --disable-shared --without-system-zlib --with-newlib --disable-libgomp --disable-libada --disable-libssp --disable-__cxa_atexit --disable-threads --disable-nls --disable-win32-registry --disable-sjlj-exceptions --with-dwarf2 --disable-libquadmath --disable-fixed-point --disable-decimal-float --with-isl=/usr/local/isl-0.15 --with-cloog=/usr/local/cloog-0.18.1 --with-gmp=/usr/local/gmp-6.2.1 --with-mpfr=/usr/local/mpfr-4.1.0 --with-mpc=/usr/local/mpc-1.2.1 --with-libiconv-prefix=/usr/local/libiconv-1.16
```

### Patches

TBD: Create patch files for binutils, libiconv, avr-libc3, etc.

# Finding/Extracting the GNU/GCC Toolchains

GNU/GCC toolchains are stored as self-extracting archives in the
[ref_app/tools/Util/MinGW/msys/1.0/local](./ref_app/tools/Util/MinGW/msys/1.0/local)
directory.

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

# Using GNU/GCC Toolchains with the `ref_app` VS Solution

The following [JPG image](./images/real-time-cpp-toolchains.jpg)
depicts the topology of the GNU/GCC toolchains in the
[real-time-cpp-toolchains](https://github.com/ckormanyos/real-time-cpp-toolchains)
repository and how these topologically harmonize with the `ref_app`
in the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository.

The GNU/GCC toolchains harmonize for use with the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository.
  - Clone the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository, which is the main companion code for the book.
  - Clone the [real-time-cpp-toolchains](https://github.com/ckormanyos/real-time-cpp-toolchains) repository, which is this repository.
  - Step 1. Extract one or more of the GNU/GCC toolchains in [ref_app/tools/Util/MinGW/msys/1.0/local](./ref_app/tools/Util/MinGW/msys/1.0/local) directory. The executable files are self-extracting archives that extract in-place where they are intended to be, such as via double-click.
  - Step 2. Following toolchain extraction(s), move or copy the [ref_app/tools](./ref_app/tools) directory to the corresponding location in the [real-time-cpp](https://github.com/ckormanyos/real-time-cpp) repository clone.
  - Open the `ref_app.sln` VisualStudio(R) solution as shown [here](./images/real-time-cpp-target-avr-build.jpg), select the solution configuration `target avr` and rebuild it. The results are placed in the temporary `ref_app/bin` directory.
