# Ortholinear tetromino keyboard QMK and gerber files
This repo contains the various QMK keyboard firmware build code. The repo also contains the PCB hardware gerber files to build various size keyboards using _tetromino PCB shapes_.

From these 5 **tetromino** base patterns (the _tetris_ game shapes), you can build pretty much any ortholinear keyboard shape, when the total number of keys is divisible by 4. See more in [Links](#links) below.

To use, drop (or symlink) [github.com/whateverany-org/qmk/keyboards/*](https://github.com/qmk/qmk_firmware/tree/master/keyboards/whateverany/) in a clone of [github.com/qmk/qmk_firmware/keyboards/](https://github.com/qmk/qmk_firmware/tree/master/keyboards).

## QMK setup, build and upload
As-built environment setup, build and flash notes.

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

```
# Environment one-time setup
mkdir -p ~/src/github.com/whateverany-org/qmk
git clone git@github.com:qmk/qmk_firmware.git
cd ~/src/github.com/qmk/qmk_firmware/keyboards
ln -s ~/src/github.com/whateverany-org/qmk/keyboards/whateverany

cd ~/src/github.com/whateverany-org/qmk
python3 -m venv .venv
source .venv/bin/activate
pip install qmk
qmk setup

# Environment everytime setup
source .venv/bin/activate

# Compile keyboards
qmk compile -kb whateverany -km badd40
qmk compile -kb whateverany -km beef60
qmk compile -kb whateverany -km babe30

# Flashing keyboards
qmk flash -kb whateverany -km badd40
qmk flash -kb whateverany -km beef60
qmk flash -kb whateverany -km babe30
```

### As-Built keyboard images
![keyboard_build_01](images/keyboard_build_01.jpg?raw=true "keyboard_build_01")

![keyboard_build_02](images/keyboard_build_02.jpg?raw=true "keyboard_build_02")

### badd40
![badd40](images/badd40.jpg?raw=true "badd40")

Originally inspired by the _[planck](https://github.com/qmk/qmk_firmware/tree/master/keyboards/planck/)_ which led me to the [40% club](https://www.40percent.club), and things like the _[let's split](https://www.40percent.club/2017/07/conjoined-lets-split.html)_, and  the _[tetrominoes](https://www.40percent.club/2019/12/tetrominoes.html)_.


### beef60
![beef60](images/beef60.jpg?raw=true "beef60")

Intended to be a keyboard for the gamers in the family.

### babe30
![babe30](images/babe30.jpg?raw=true "babe30")

Inspired by the [gherkin](https://www.40percent.club/2016/11/gherkin.html).

## Hardware
The Gerber files are now in here [github.com/whateverany-org/qmk/git.40percent.club.tetrominoes](https://github.com/whateverany-org/qmk/tree/main/git.40percent.club.tetrominoes) under the original [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

### Parts list

| Part | Unit | Total |
| +--- | ---+ | ----+ |
| [JCLPCB PCB fabrication (25xT, 25xL, 25xS, 25xStick & 25xCube)](https://jlcpcb.com/) | 1xAU$39.36 + AU$20.48 shipping  | AU$59.84 |
| [3PCS/LOT ATmega32U4 Pro Micro Dev Board (x2)](https://www.aliexpress.com/item/32952028063.html) | 2xAU$15.92  | AU$31.83 |
| [200PCS/LOT Outemu Brown Key Switches](https://www.aliexpress.com/item/1005001864766812.html) | 1xAU$53.41  | AU$53.41 |
| [110PCS/LOT Keycaps (140xGray, 40xRed & 40xBlack)](https://www.aliexpress.com/item/32830177884.html) | 2xAU$27.33  | AU$50.88 |
| [110PCS/LOT Keycaps (60xgreen, 50xyellow, 50xorange & 60xblue)](https://www.aliexpress.com/item/32832417476.html) | 2xAU$25.44  | AU$54.65 |
| [100PCS/LOT 1N4148 Diodes (x3)](https://www.aliexpress.com/item/1005002339916163.html) | 3xAU$2.96  | AU$8.86 |
| [100PCS/LOT 0ohm Resistors](https://www.aliexpress.com/item/32952657927.html) | 3xau$3.31  | au$9.93 |

**au$269.40 total** (or 6 keyboards @ au$44.90 per keyboard)

## microcontrollers
various microcontrollers tried. some of these microcontrollers may just be surplus stock from other iot projects, not specifically for qmk.

### bluepill (atmega32u4)
originally build using the atmega32u4 pro micro dev (microusb) - see [parts list](#parts-list).

### **rp2040**

| part | unit | total |
| +--- | ---+ | ----+ |
| [rp2040 pico board](https://www.aliexpress.com/item/1005003371056277.html) | 1xau$5.81  | au$5.81 |

a dream to program, compared to everything else. has onboard rgb led.

Keen to try this one next:

| Part | Unit | Total |
| +--- | ---+ | ----+ |
| [RP2040-Zero Pico](https://www.aliexpress.com/item/1005007650325892.html) | 10xAU$3.37  | AU$33.65 |

### Bluepill V2 (STM32)
Tried the "_STM32_" compatible CH32F103C8T6 - too much of a hassle programing/flashing.

| Part | Unit | Total |
| +--- | ---+ | ----+ |
| [CH32F103C8T6 USB-C](https://www.aliexpress.com/item/32719680030.html) | 10xAU$3.56  | AU$35.75 |

```
./isp55e0/isp55e0 --debug -f .build/whateverany_badd40_default.bin
```

### Blackpill (NRF52840 with bluetooth)
Not officially supported by QMK, fork projects are somewhat complex/limited.

| Part | Unit | Total |
| +--- | ---+ | ----+ |
| [NRF52840 Nice!Nano dev board](https://www.aliexpress.com/item/1005007097467339.html) | 8xAU$8.52  | $AU$68.33 |

### HC-05 bluetooth
Can be used with a microcontroller to add bluetooth (I2C?).

| Part | Unit | Total |
| +--- | ---+ | ----+ |
| [HC-05 6 pin](https://www.aliexpress.com/item/32340945238.html) | 6x$4.23  | AU$25.39 |

## Links
- [40percent.club tetrominoes blog article](http://www.40percent.club/2019/12/tetrominoes.html)
  - Gerber files [git.40percent.club/di0ib/Misc/tetrominoes](https://git.40percent.club/di0ib/Misc/src/branch/master/tetrominoes) (**DEFUNCT** since [~2025-JAN-26](https://web.archive.org/web/20250126081724/https://git.40percent.club/di0ib/Misc/src/branch/master/tetrominoes) and missing from [github.com/di0ib/Misc](https://github.com/di0ib/Misc))
    - Now archived to [github.com/whateverany-org/qmk/git.40percent.club.tetrominoes](https://github.com/whateverany-org/qmk/tree/main/git.40percent.club.tetrominoes) under [Creative Commons Attribution-ShareAlike 4.0 International License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png) after finding here [github.com/Ardakilic/git.40percent.club/tetrominoes](https://github.com/Ardakilic/git.40percent.club/tree/master/tetrominoes)
- [redit article](https://www.40percent.club/2019/12/tetrominoes.html)
- [kbd.news article](https://kbd.news/Tetrominoes-in-action-751.html)
