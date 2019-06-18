Install Warframe from Steam.

You will need to install wine and all of its dependencies, as Proton does not come with all of the required packages.

Install Wine, Winetricks, xboxdrv, and other dependencies:
```
yay -Syu xboxdrv xz-utils curl tar gzip xterm wine winetricks wine-mono wine_gecko
```

Install xboxdrv as a service:
```
sudo systemctl enable xboxdrv
sudo systemctl start xboxdrv
```

Go to Warframe Wine folder: `/home/{username}/.steam/steam/steamapps/compatdata/230410/pfx`

Run in Terminal: `WINEPREFIX=$(pwd) winetricks xact`

Start the Game!
