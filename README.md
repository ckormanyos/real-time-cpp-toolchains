# real-time-cpp GNU/GCC Toolchains on Windows

This repository is intended to store GNU/GCC toolchains needed for building `ref_app` targets for the repository [real-time-cpp](https://github.com/ckormanyos/real-time-cpp). These GNU/GCC toolchains are built to run on Windows(R).

This is work in progress.

# Using the Toolchains

GNU/GCC toolchains are stored as self-extracting archives in the [ref_app/tools/Util/MinGW/msys/1.0/local directory](./ref_app/tools/Util/MinGW/msys/1.0/local).

Consider, for instance, the `gcc-avr` toolchain version 7.3.0. It is stored in the executable file `gcc-7.3.0-avr.exe`. This file can be extracted (i.e., vie double click or suitable command on the command line (cmd).

Upon extraction of one or more of the toolchains, the entire contents of of the `tools` directory are intended to be moved or copied to the `ref_app` folder in [real-time-cpp](https://github.com/ckormanyos/real-time-cpp). For instance, `tools` is copied or dragged-and-dropped to the `ref_app` directory of [real-time-cpp](https://github.com/ckormanyos/real-time-cpp), creating the directory `ref_app\tools\...` ther, then the MSVC GNU/GCC target builds work out-of-the-box in VisualStudio.
