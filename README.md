# rnnoise-win64 [![build](https://github.com/gavv/rnnoise-win64/actions/workflows/build.yml/badge.svg)](https://github.com/gavv/rnnoise-win64/actions/workflows/build.yml)

Prebuilt [RNNoise](https://github.com/xiph/rnnoise) static library for 64-bit MSVC.

Binaries are built and published automatically using Github Actions. You can either use binaries from this repo, or fork the repo and configure your own build, so that you can completely trust the build results.

Branch    | Description
--------- | ------
[`main`](https://github.com/gavv/rnnoise-win64) | build script and github actions config
[`pkg`](https://github.com/gavv/rnnoise-win64/tree/pkg) | built binaries

The library is built using CMake with Visual Stduio 2019 LLVM compiler toolchain. It is binary-compatible with MSVC.
