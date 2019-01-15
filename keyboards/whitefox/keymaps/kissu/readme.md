# How to basically flash my Fox (under Ubuntu 18.04)

👿 Do not forget the damn `make git-submodule` (_will I one day learn what this command is doing ?_)

Start by making some custom stuff with the layout, when done, simply run `make whitefox:kissu`.

Then `sleep 10 && dfu-util -D whitefox_kissu.bin` optionnaly, append: `-S mk20dx256vlh7` or `-j8` (use 8 cores) too. During the 10 seconds delay, rush to the button to enter `DFU` state.

⚠️ For some reason, my newly fresh `RESET` (right fn + print screen) button is not working... (download fails) ⚠️

Todo
---
- [ ] see how the `Shift` layer impacts the whole system, and if it's not better to just send regular unicode scancodes
- [ ] finish reading [the cool blog](https://thomasbaart.nl/category/mechanical-keyboards/firmware/qmk/qmk-basics/)
- [ ] **finish** the damn Carpalx pages and choose if I want an `Halmak` or one alternative, when done, I guess making the layout somewhere would be a nice idea

## Type Fu setup
This is how you should proceed to add any kind of keymap to the app !

This is the commadn to find out the place in which the config files of `Type Fu` are stored: `grep -rnwl ~/.config/google-chrome/Default/Extensions -e "proverbs-en"`, something like `...id/versions/layouts`
