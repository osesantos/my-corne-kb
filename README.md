# my-corne-kb
This is my current corne keyboard config, using qmk

**corne - corne aurora rev1.0**

## utils

qmk configurator - https://config.qmk.fm/
qmk documentation - https://docs.qmk.fm/

## how to compile?

First setup the qmk environemnt

check - https://docs.qmk.fm/#/newbs_getting_started

### via .c files

```bash
qmk compile -kb splitkb/kyria/rev1 -km default
```

### via json files

go to the qmk configurator and import the json file

```bash
qmk compile file.json
```

## how to flash?

### via .c files

```bash
qmk flash -kb splitkb/kyria/rev1 -km default
```

### via json files

go to the qmk configurator and import the json file

```bash
qmk flash file.json
```

## Troubleshoot
- if you get an error like `Error: Bootloader not found. Trying again in 5s.` you need to press the reset button on the keyboard.
- if you get an error like `Error: Bootloader not found. Trying again in 5s.` and you need to specify the bootloader, you can do it like this `qmk flash -kb splitkb/kyria/rev1 -km default -bl avrdude`.
- if you get an error like `Error: Bootloader not found. Trying again in 5s.` and you need to specify the bootloader in the `rules.mk` file, you can do it by adding the line `BOOTLOADER = caterina` in the `rules.mk` file.
- if only one half of the keyboard is working, you need to flash the other half as well.
- if only one half of the keyboard is working, you need to add to the `config.h` file the `#define SPLIT_USB_DETECT` line.

*Note:* using the json may not work for all keyboards, due to the rules, so it is better to use the `.c` files.
