# qmk
QMK keyboards

Small repo with custom whateverany keyboard code, maps and tools.

To compile, symlink keyboards to qmk_firmware/keyboards. e.g.

```
mkdir -p ~/src/github.com/whateverany-org/qmk
git clone git@github.com:qmk/qmk_firmware.git
cd ~/src/github.com/qmk/qmk_firmware/keyboards
ln -s ~/src/github.com/whateverany-org/qmk/keyboards/whateverany

cd ~/src/github.com/qmk/qmk_firmware
python3 -m venv .venv
source .venv/bin/activate
pip install qmk
qmk setup
```

## babe30
![babe30](images/babe30.jpg?raw=true "babe30")

## badd40

![badd40](images/badd40.jpg?raw=true "badd40")

### about
*Based on 0_sixty*

* Keyboard Maintainer: [whateverany](https://github.com/whateverany)
* Hardware Supported: *The PCBs, controllers supported*
* Hardware Availability: *Links to where you can find this hardware*

Make example for this keyboard (after setting up your build environment):

```
qmk compile -kb whateverany -km badd40
```

Flashing example for this keyboard:
```
qmk flash -kb whateverany -km badd40
```

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

## beef60
![beef60](images/beef60.jpg?raw=true "beef60")

# Build images
![keyboard_build_01](images/keyboard_build_01.jpg?raw=true "keyboard_build_01")
![keyboard_build_02](images/keyboard_build_02.jpg?raw=true "keyboard_build_02")

# microcontrollers

./isp55e0/isp55e0 --debug -f .build/whateverany_badd40_default.bin
