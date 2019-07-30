Install Wormd W.M.D from Steam.

Install some dependencies:
```bash
sudo pacman -Syu libcurl-gnutls vulkan-radeon opencl-mesa mesa-libgl
```

Follow the instructions here: https://steamcommunity.com/app/327030/discussions/2/133257959065155871/

In case that post is ever deleted here is a copy of it:
> # Introduction
> I was having a lot of issues trying to get it to run on Arch Linux, but it finally runs!
> So, for anyone else having problems, I'm going to post what worked for me.
> It might be different for you, depending on how your system is already setup, but it's a place to start.
> 
> # Summary
> I had to install libcurl-gnutls and modify the Run.sh as posted below.

> # The journey
> Initially, the game didn't start at all, but starting the game from console revealed that I was missing libcurl-gnutls.so.4.
> So I installed the package, but that didn't quite do the trick. I eventually built it myself and it worked. However, I believe this to be unnecessary. I have > since reinstalled the package and it still works fine.
> 
> After that, I was able to start the game from console, but it still crashed when I tried to open it from steam. I didn't really care, though, since it seemed to > work from console.
> Alas, I got to hear some music and soon after it froze and eventually crashed. On some attempts I even got to see the main menu before it eventually died.
> 
> The console output seemed to reveal that it is a problem with dbus, but what exactly was going on, I had no idea.
> 
> Lots of googleing later, I finally figured out that it seems to be an issue with Arch's libdbus being too new. The solution to this problem is to preload the > dbus libraries steam ships with, which is explained here.
> 
> The script you see there probably works, but I dislike how it puts everything on one line. All you really need to do is add this line to after the two export > statements:
> ```
> export LD_PRELOAD="$(
>     printf "%s " ~/.steam/SteamApps/common/WormsWMD/lib/libQt5*.so* \
>         ~/.steam/steam/ubuntu12_32/steam-runtime/amd64/lib/x86_64-linux-gnu/libdbus-1.so.3 \
>         ~/.steam/steam/ubuntu12_32/steam-runtime/amd64/lib/x86_64-linux-gnu/libdbus-1.so.3.5.8
> )"
> ```
> 
> Depending on how old or new your installation is, you might have to lowercase "SteamApps". Your game might also be installed in a different location.
> 
> The final Run.sh then looks like this:
> ```
> #!/bin/bash
> 
> export LC_ALL=C
> export LD_LIBRARY_PATH="/usr/lib:/usr/local/lib"
> export LD_PRELOAD="$(
>     printf "%s " ~/.steam/SteamApps/common/WormsWMD/lib/libQt5*.so* \
>         ~/.steam/steam/ubuntu12_32/steam-runtime/amd64/lib/x86_64-linux-gnu/libdbus-1.so.3 \
>         ~/.steam/steam/ubuntu12_32/steam-runtime/amd64/lib/x86_64-linux-gnu/libdbus-1.so.3.5.8
> )"
> 
> chmod a+x ./Worms\ W.M.Dx64
> ./Worms\ W.M.Dx64
> ```
> 
> With this, the game should work and it even works when running through steam! \o/
> 
> If you were having trouble running the game on Arch, give this a try and maybe that works already for you. If it doesn't and you figure out the issue, please > post here so we can help more people get the game running.

After that you should be good to go!