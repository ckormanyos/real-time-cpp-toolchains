# GNU/GCC Toolchains for real-time-cpp on Windows

This repository is intended to store GNU/GCC toolchains needed
for building `ref_app` targets for the repository
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).
These GNU/GCC toolchains are built to run on Windows(R).

# Using the Toolchains

GNU/GCC toolchains are stored as self-extracting archives in the
[ref_app/tools/Util/MinGW/msys/1.0/local directory](./ref_app/tools/Util/MinGW/msys/1.0/local).

Consider, for instance, the `gcc-avr` toolchain version 7.3.0.
It is stored in the executable file `gcc-7.3.0-avr.exe`.
This file can be extracted, for example, via double click
or suitable command on the command line (cmd).

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

# Detailed Instructions for the `ref_app` VS Solution

TBD
