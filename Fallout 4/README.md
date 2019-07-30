Install Fallout 4 from Steam.

Right click the game and click properties.
Click "Set launch options" and add the following:
```
WINEDLLOVERRIDES="xaudio2_7=n,b" PROTON_NO_ESYNC=1 %command%
```

Edit this file, you may need to change it slightly if you installed the game to a different location: `~/.local/share/Steam/steamapps/compatdata/377160/pfx/drive_c/users/steamuser/My Documents/My Games/Fallout4/Fallout4.ini`.

Add this to the `[Controls]` section:
```
bBackgroundMouse=1
```

Open winecfg (again changing it slightly if the game is installed somewhere else):
```bash
WINEPREFIX=~/.local/share/Steam/steamapps/compatdata/377160/pfx/
winecfg
```

Check "Automatically capture the mouse in full-screen windows"
Check "Emulate a virtual desktop" and set it to your resoulution.

You should be ready to play!