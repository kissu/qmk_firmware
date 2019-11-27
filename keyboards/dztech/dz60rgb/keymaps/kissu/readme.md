Let's try to get that kind of simple working layout !
![Standard 60% ANSI layout](https://i.redd.it/17mdpyzkf0u21.png)

So, to flash a [`dz60rgb-ansi`](https://kbdfans.cn/collections/60/products/dz60rgb-ansi-mechanical-keyboard-pcb), you will need to run `sudo dfu-util -d 0483:df11 -a 0 -s 0x08000000:leave -D dztech_dz60rgb_kissu.bin` (if you need more info about the flags passed, use `dfu-util help`).

The `.bin` and `.hex` will be available at the root of the repo and also in `qmk_firmware/.build` hidden directory.

You can have all the cool stuff from the [QMK Configurator](https://config.qmk.fm/#/dztech/dz60rgb/LAYOUT):

-   the `keymap.json` to get a backup later on or to host it somewhere for quick sharing for folks
-   the `keymap only` will give the `keymap.c` (to compile later in into the needed `.bin` file) and `layers.json` (not sure what it is for tho, maybe mandatory in pair with the C file)
-   the `firmware` is the `.bin` itself, ready to be flashed on the PCB
-   the `full source` is REALLY useless to download since it's pretty much the whole QMK repo with your own keymap added to it (_I guess_)

But do not forget to press the `compile` button for all the cool stuff (_but the `keymap.json` ofc_)
NEED TO DOUBLE CHECK all the _italics_

If you want to compile a keymap, use `sudo make dztech/dz60rgb:<keymap>:dfu-util` but from the root of the repo !! aka `qmk_firmware` and not deeper, or it won't work...

## Questions

-   [ ] Why some files are `.bin` and other are `.hex` ?? (I guess it depends of the board...)
        Actually, v1 PCB version is ARM (.bin) and v2 is AVR (.hex) files, my PCB is currently v1
-   [ ] What is the main differences between a `.c` and a `.h` keymap way of doing things ? Just depends of the place where it does from ?? (or depends of the generator apparently)

sudo dfu-util -d 0483:df11 -a 0 -s 0x08000000:leave -D tasty.hex
