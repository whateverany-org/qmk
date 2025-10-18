# Ortholinear tetromino keyboard QMK and gerber files
This repo contains the various QMK keyboard firmware build code. The repo also contains the PCB hardware gerber files to build various size keyboards using _tetromino PCB shapes_.

From these 5 **tetromino** base patterns (the _tetris_ game shapes), you can build pretty much any ortholinear keyboard shape, when the total number of keys is divisible by 4. See more in [Links](#links) below.

To use, drop (or symlink) [github.com/whateverany-org/qmk/keyboards/*](https://github.com/qmk/qmk_firmware/tree/master/keyboards/whateverany/) in a clone of [github.com/qmk/qmk_firmware/keyboards/](https://github.com/qmk/qmk_firmware/tree/master/keyboards).

## QMK setup, build and upload
As-built setup, build and upload notes
```
mkdir -p ~/src/github.com/whateverany-org/qmk
git clone git@github.com:qmk/qmk_firmware.git
cd ~/src/github.com/qmk/qmk_firmware/keyboards
ln -s ~/src/github.com/whateverany-org/qmk/keyboards/whateverany

cd ~/src/github.com/whateverany-org/qmk
python3 -m venv .venv
source .venv/bin/activate
pip install qmk
qmk setup
```

### babe30
![babe30](images/babe30.jpg?raw=true "babe30")

### badd40

![badd40](images/badd40.jpg?raw=true "badd40")

#### about
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

### beef60
![beef60](images/beef60.jpg?raw=true "beef60")

# Build images
![keyboard_build_01](images/keyboard_build_01.jpg?raw=true "keyboard_build_01")
![keyboard_build_02](images/keyboard_build_02.jpg?raw=true "keyboard_build_02")

# microcontrollers

./isp55e0/isp55e0 --debug -f .build/whateverany_badd40_default.bin

## Hardware
- [github.com/whateverany-org/qmk/git.40percent.club.tetrominoes](https://github.com/whateverany-org/qmk/tree/main/git.40percent.club.tetrominoes) under the original [Creative Commons Attribution-ShareAlike 4.0 International License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)

### Parts list
- AU$59.84 = 1xAU$39.36 + AU$20.48 shipping [JCLPCB PCB fabrication (25xT, 25xL, 25xS, 25xStick & 25xCube)](https://jlcpcb.com/)
- AU$31.83 = 2xAU$15.92 [3PCS/LOT ATmega32U4 Pro Micro Dev Board (x2)](https://www.aliexpress.com/item/32952028063.html)
- AU$53.41 = 1xAU$53.41 [200PCS/LOT Outemu Brown Key Switches](https://www.aliexpress.com/item/1005001864766812.html)
- AU$50.88 = 2xAU$27.33 [110PCS/LOT Keycaps (140xGray, 40xRed & 40xBlack)](https://www.aliexpress.com/item/32830177884.html)
- AU$54.65 = 2xAU$25.44 [110PCS/LOT Keycaps (60xgreen, 50xyellow, 50xorange & 60xblue)](https://www.aliexpress.com/item/32832417476.html)
- AU$8.86 = 3xAU$2.96 [100PCS/LOT 1N4148 Diodes (x3)](https://www.aliexpress.com/item/1005002339916163.html)
- AU$9.93 = 3xAU$3.31 [100PCS/LOT 0ohm Resistors](https://www.aliexpress.com/item/329Diodes52657927.html)
- **AU$269.40 TOTAL**

## Links
- [40percent.club tetrominoes blog article](http://www.40percent.club/2019/12/tetrominoes.html)
  - Gerber files [git.40percent.club/di0ib/Misc/tetrominoes](https://git.40percent.club/di0ib/Misc/src/branch/master/tetrominoes] (**DEFUNCT** since [~2025-JAN-26](https://web.archive.org/web/20250126081724/https://git.40percent.club/di0ib/Misc/src/branch/master/tetrominoes) and missing from [github.com/di0ib/Misc](https://github.com/di0ib/Misc))
    - Now archived to [github.com/whateverany-org/qmk/git.40percent.club.tetrominoes](https://github.com/whateverany-org/qmk/tree/main/git.40percent.club.tetrominoes) under [Creative Commons Attribution-ShareAlike 4.0 International License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png) after finding here [github.com/Ardakilic/git.40percent.club/tetrominoes](https://github.com/Ardakilic/git.40percent.club/tree/master/tetrominoes)
- [redit article](https://www.40percent.club/2019/12/tetrominoes.html)
- [kbd.news article](https://kbd.news/Tetrominoes-in-action-751.html)
