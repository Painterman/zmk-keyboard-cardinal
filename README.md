# ZMK Module for Cardinal keyboards

This repository contains the shield definitions for the [Cardinal keyboard](https://github.com/Painterman/Cardinal), allowing to build firmware without needing to clone [my personal keymap](https://github.com/Painterman/zmk-config-cardinal) (but feel free to peek around) 

## Usage

This repository assumes you are at least a bit familiar with the zmk docs and have at least a surface understanding of [zmk modules](https://zmk.dev/docs/features/modules) and how to use then to build your own firmware.

In short, add this module to your ´west.yml´, like shown:

```
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    # Add the remote repository
    - name: painterman
      url-base: https://github.com/painterman
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    # Add the module to build
    - name: zmk-keyboard-cardinal
      remote: painterman
      revision: main
  self:
    path: config
```
And you should be able to build your own firmware providing your own keymap. This repository contains a example '.keymap', use it as a jumping point.

## Extra

This module is [zmk studio](https://zmk.dev/docs/features/studio) ready as well as [keymap editor](https://github.com/nickcoutsos/keymap-editor) ready, includes a 'cadinal.json' with the key positions for it.

If your encounter any issues please let me know, i may or may not have build a firmware using the module version.
