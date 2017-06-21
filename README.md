# Ethminer for macOS

## Meta
- Current Version: **1.0.2**
- Release Date: **June 20, 2017**
- Also known as _cpp-ethereum_ and _c++-ethereum_.
- Ethereum Donations:
  - Me: 0x1e8cce03A2C01d18C5a68F410bfE34eea1aa16f2
  - Genoil: 0xeb9310b185455f863f526dab3d245809f6854b4d

## Summary
This is a fork of the [cpp-ethereum](https://github.com/ethereum/cpp-ethereum) project that works on macOS 10.12.x (Sierra).

This specific repo was forked from [Genoil's cpp-ethereum Repo](https://github.com/Genoil/cpp-ethereum), which itself was forked from the official aforementined repo. This fork was made in response to the lack of maintained macOS support from Genoil's fork and from the [Official Homebrew Ethereum Formula](https://github.com/ethereum/homebrew-ethereum/).

The conversation that led to this fork can be found at https://github.com/ethereum/homebrew-ethereum/issues/116.

## Pre-Installation Instructions
Download and install the latest version of
- Xcode from Apple at https://developer.apple.com/xcode
- Homebrew from https://brew.sh

## Installation Instructions

1. Download this fork of cpp-ethereum
```
git clone --recursive https://github.com/ArtSabintsev/cpp-ethereum.git
```

2. Enter the downloaded folder and create and enter the `build` directory.
```
mkdir build; cd build
```

3. Run _one of the the following_ `cmake` calls on the root directory from within the `build` directory.
  - This will also install all the homebrew dependencies that you'll need.
```
// RUN THIS IF YOU HAVE AN NVIDIA CARD AND WANT PROPRIETARY DRIVERS.
cmake -DBUNDLE=cudaminer -DETHSTRATUM=1 ..

// RUN THIS IF YOU HAVE ANY CARD (INCL. NVIDIA) AND WANT THE OPEN SOURCE 'OpenCL' DRIVERS.
cmake -DBUNDLE=miner -DETHSTRATUM=1 ..
```

4. Run `make` next:
```
make -j8
```

5. Afterwards, run `cmake` again, but on your current directory, the build directory.
```
cmake --build .
```

## Launching `ethminer`
Once installation succedes, go to the `ethminer` directory (from the build directory). Type in `./ethminer` and you're good to go.

## Support
While I am a full-time programmer, I do not use C/C++ in my daily life, at least not at a level where I can actively develop this fork. However, with that being said, I will do my best to maintain this fork as issues arise.


## Maintained By
[Arthur Ariel Sabintsev](http://www.sabintsev.com)
