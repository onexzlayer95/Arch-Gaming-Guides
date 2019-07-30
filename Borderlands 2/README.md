Install Borderlands 2 from Steam. While this game has Native support, I wasn't able to get it to run.

Right-Click the game in your library > Properties > Check "Force the use of a specific Steam Play compatability tool".

Run in Terminal:
```
cd /home/{username}/.steam/steam/steamapps/common/Borderlands 2/Binaries/Win32
rm Launcher.exe
ln -sf Borderlands2.exe Launcher.exe
```

Start the Game!
