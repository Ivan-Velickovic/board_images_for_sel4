# Flashable images for seL4 development

This repository aims to provide ready-to-go, reproducible, images
that can be used for seL4 development.

All images are available for download from the
[releases page](https://github.com/au-ts/board_images_for_sel4/releases/latest).

## Available images

There are prebuild images available for the following platforms:

* Avnet MaaXBoard
* HardKernel Odroid-C4
* Raspberry Pi 4B
* Pine64 RockPRO64

### Usage

Once you download the image for your board, you need to flash it to your storage device.
You can do this with [the balenaEtcher application](https://etcher.balena.io/) or the `dd` utility
on the command line.

## Building from source

To build from source you must be using Linux and have [Nix](https://nixos.org/download/)
installed.

To build all available images from source, run:
```
nix build .
```

The images will be in `result/`.

For each board there are two artifacts:
* Compiled U-Boot
* Flashable image (e.g for microSD card or eMMC)

To build a specific package run:
```
nix build .#<BOARD>-<ARCHITECTURE>-<ARTIFACT>
```

For example, to build the image for the Raspberry Pi 4B:
```
nix build .#rpi4-aarch64-image
```

The image will be in `result/`.

