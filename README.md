## Chizuhoru - screenshot tool for Linux  

<img align="right" width="400" height="300" src="https://i.imgur.com/iwXcJS7.png">  


## Features:

- Edit screenshots!
- Silent screenshots with CLI
- Shadows!
- Anonymous upload to Imgur
- Custom uploads!
- Steganography?

## Requirements

### Easy install
Install XClip (see below).  
Run `install.sh` to create virtualenv and gather all needed modules. Now you can run `chizuhoru` and bind PrtScr to it for convenience.

### Packages

- Python **3.7+**
- XClip (read [Clipboard persistence](https://wiki.ubuntu.com/ClipboardPersistence))
  + `apt install xclip` for Ubuntu/Debian
  + `pacman -S xclip` for Arch Linux
- PyQt5
  + `apt install python3-pyqt5 pyqt5-dev-tools` for Ubuntu/Debian
  + `pacman -S pyqt5-common python-pyqt5` for Arch Linux
  + as for 2019, `python3 -m pip install PyQt5` also works fine.

### Modules
Single command:  
`python3 -m pip install -r requirements.txt`  

Manually:
- Python Image Library
  + `python3 -m pip install Pillow`
- [Python MSS](https://github.com/BoboTiG/python-mss)
  + `python3 -m pip install mss`
- Python Aggdraw
  + `python3 -m pip install aggdraw` 
- Requests
  + `python3 -m pip install requests`  
- Xlib
  + `python3 -m pip install Xlib`
  
## Usage
You can pass arguments both to `main.py` or `chizuhoru` generated by `install.sh`, so `./chizuhoru` is equal to `python3 chizuhoru/py/main.py`.  
 
- Run in GUI:
    ```shell
    ./chizuhoru
    ```   
- Make a silent fullscreen shot, copy to clipboard:
    ```shell
    chizuhoru -s
    ```  
- Set default directory instead of `/home/user/`. If present, <kbd>Enter</kbd> and <kbd>U</kbd> hotkeys will copy/upload image AND save it to the directory provided.
    ```shell
    chizuhoru -d /home/user/Pictures
    ```  
- Make a silent fullscreen shot, save to the directory:
    ```shell
    chizuhoru -s -d /home/user/Pictures
    ```  
- Select screen to grab. Default: -1 (all screens):
    ```shell
    chizuhoru -s -m 0
    ```
- Launch from tray: just re-run script or click at the tray icon.  
 
## Hotkeys

|  Keys                                                                     |  Description                     |
|---                                                                        |---                               |
| <kbd>T</kbd>                                                              | Show toolkit                     |
| <kbd>S</kbd>                                                              | Open save / upload dialog        |
| <kbd>A</kbd>                                                         | Select window under the mouse pointer |
| <kbd>Esc</kbd>                                                            | Exit                             |
| <kbd>Enter</kbd> | Copy selected rectangle to clipboard. If there is no selection, fullscreen will be copied |
| <kbd>U</kbd>                           | Upload selection to imgur and copy link to clipboard, same as Enter |
| <kbd>Ctrl</kbd> + <kbd>Z</kbd>                                            | Undo                             |
| <kbd>Mouse wheel</kbd>                                                    | Increase/decrease tool thickness |
  
## Custom uploads
Chizuhoru has a simple frontend for python requests module to manage headers and payload. It supports simple API and can search for response link through html output.
It also has presets for uguu.se and catbox.moe.  

## Steganography
Chizuhoru can hide text in your pictures by changing red channel's least significant bit. Who really needs it? No one. That's the point.

Encoding                   |  Decoding
:-------------------------:|:-------------------------:
![](https://i.imgur.com/vBbwzf9.png)  |  ![](https://i.imgur.com/CJ2SJ1y.png)


## Environments

Environments checked:  

- i3 WM + Compton
- Openbox WM + Compton
- XFCE
- Deepin DE
- KDE

## TODO

- [ ] Webdav uploads
- [ ] Remove spaghetti

## Frequently asked questions

**Q**: Why Python?  
**A**: uhhhhhhhhhhh...  
