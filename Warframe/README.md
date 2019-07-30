Install Warframe from Steam.

You will need to install wine and all of its dependencies, as Proton does not come with all of the required packages.

Install Wine, Winetricks, and other dependencies:
```bash
sudo pacman -Syu curl tar gzip xterm wine-staging winetricks wine-mono wine_gecko
```

Install xboxdrv as a service:
```bash
yay xboxdrv
sudo systemctl enable xboxdrv
sudo systemctl start xboxdrv
```

You will need to use GloriousEggroll's custom version of Proton. 
Download and extract this archive: https://github.com/GloriousEggroll/proton-ge-custom/releases/download/4.11-GE-1/Proton-4.11-GE-1.tar.gz

Follow these instructions to install and enable it:
```bash
mkdir ~/.steam/root/compatibilitytools.d
mv ~/Downloads/Proton-4.11-GE-1 ~/.steam/root/compatibilitytools.d/Proton-4.11-GE-1
# Close and re-open steam
# Right click Warframe and click Properties
# At the bottom of the General tab, Check "Force the use of a specific Steam Play compatibility tool"
# Then select Proton-4.11-GE-1 from the drop down and click CLOSE.
```

Start the Game!
