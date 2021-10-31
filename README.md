# GNU/GCC Toolchains for real-time-cpp on Windows

This repository is intended to store GNU/GCC toolchains needed
for building `ref_app` targets for the repository
[real-time-cpp](https://github.com/ckormanyos/real-time-cpp).
These GNU/GCC toolchains are built to run on Windows(R).

# Finding/Extracting the GNU/GCC Toolchains

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

# Instructions using GNU/GCC Toolchains in `ref_app` VS Solution

The GNU/GCC toolchains harmonize for use with the [real-time-cpp repository](https://github.com/ckormanyos/real-time-cpp).
  - Clone the [real-time-cpp repository](https://github.com/ckormanyos/real-time-cpp), which is the main companion code for the book.
  - Clone the [real-time-cpp-toolchains repository](https://github.com/ckormanyos/real-time-cpp-toolchains), which is this repository.
  - Extract one or more of the GNU/GCC toolchains in [ref_app/tools/Util/MinGW/msys/1.0/local directory](./ref_app/tools/Util/MinGW/msys/1.0/local).
  - The executable files are self-extracting archives that extract in-place where they are intended to be, such as via double-click.
  - Following toolchain extraction(s), move or copy the [ref_app/tools directory](./ref_app/tools) to the corresponding location in the [real-time-cpp repository](https://github.com/ckormanyos/real-time-cpp) clone.



The [following JPG image](./images/real-time-cpp-toolchains.jpg) sketches these details and how the topology is arranged.
