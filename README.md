# qmk
QMK keyboards

Small repo with custom whateverany keyboard code, maps and tools.

To compile, symlink keyboards to qmk_firmware/keyboards. e.g.

```
mkdir -p ~/src/github.com/whateverany-scratch/qmk
git clone git@github.com:qmk/qmk_firmware.git
cd ~/src/github.com/qmk/qmk_firmware/keyboards
ln -s ~/src/github.com/whateverany-scratch/qmk/keyboards/whateverany

cd ~/src/github.com/qmk/qmk_firmware
python3 -m venv .venv
source .venv/bin/activate
pip install qmk
qmk setup
qmk compile -kb whateverany -km badd40
```

## babe30
![babe30](images/babe30.jpg?raw=true "babe30")
## badd40
![badd40](images/badd40.jpg?raw=true "badd40")
## beef60
![beef60](images/beef60.jpg?raw=true "beef60")

# Build images
![keyboard_build_01](images/keyboard_build_01.jpg?raw=true "keyboard_build_01")
![keyboard_build_02](images/keyboard_build_02.jpg?raw=true "keyboard_build_02")

