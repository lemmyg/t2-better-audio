# Zero Configuration Audio for Macs with the T2 Chip

Currently, someone who wants to run linux on their T2 Mac must install the audio files manually depending on their model. Though with [this patch](https://github.com/kekrby/apple-bce/commit/170e7ad37166319f1a13b37e52f83a43608826b5.patch), it becomes possible for different configuration files to coexist. This repository contains the configuration files with the necessary changes made to work with the changes in the `apple-bce` driver. Both `pipewire` and `pulseaudio` are supported, but `pipewire` works better in general.

The files are based on `https://gist.github.com/MCMrARM/c357291e4e5c18894bea10665dcebffb`, `https://gist.github.com/kevineinarsson/8e5e92664f97508277fefef1b8015fba` and `https://gist.github.com/bigbadmonster17/8b670ae29e0b7be2b73887f3f37a057b`.

# Installation

Clone this repo and `cd` into it, then run these commands:

```
cp files/alsa-card-configs/* /usr/share/alsa/cards/
cp files/profile-sets/* /usr/share/alsa-card-profile/mixer/profile-sets/
cp files/91-pulseaudio-custom.rules /usr/lib/udev/rules.d/
```

Note that some distributions (for example NixOS) may have different ways to install the files.
