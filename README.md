Orbweaver-Xkb
=============
This XKB (X keyboard extension), change the default setup of the Razer
Orbweaver, to a setup like:
```
F1 F2 F3 F4 F5
1  2  3  4  5
6  7  8  9  0
F6 F7 F8 F9 F10
                LCTL
                  Up
                Left Right
                  Down
                  
                  Space
```

## Usage
Checkout this repo then, use xinput to get the right id
```
$ cat xinput 
⎡ Virtual core pointer                          id=2    [master pointer  (3)]
⎜   ↳ Razer Razer Orbweaver                     id=14   [slave  pointer  (2)]
⎜   ↳ Razer Razer Orbweaver                     id=15   [slave  pointer  (2)]
⎣ Virtual core keyboard                         id=3    [master keyboard (2)]
    ↳ Razer Razer Orbweaver                     id=13   [slave  keyboard (3)]
```

Make sure to change the keyboard mapping of the orbweaver to us
```
$ setxkbmap -device 13 -layout us
```

The use xkbcomb to load it on the dedicated device
```
$  xkbcomp -i 13 -w0 orbweaver.xkb $DISPLAY
```

## Licence
The project is GPLv3.
