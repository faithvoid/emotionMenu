# emotionMenu
A CRT-specific frontend for multipurpose Raspberry Pi setups, mimicking the Playstation 2 aesthetic. Written in Python with Pygame and the AV library.
## Why?
I've recently set up a Raspberry Pi 5 as an all-in-one retro gaming / media setup via installing Raspberry Pi OS, EmulationStation, XFCE4, Kodi, and a bunch of other goodies, and realized I didn't have a good way to swap between them all with both a keyboard/mouse setup or a controller, so I threw this together over the weekend as a basic but pretty launcher for EmulationStation, GunCon2 calibration, Kodi, and launching XFCE, but any and all launchers can be modified to your liking!

## Installation
- Download the latest release .zip
- Extract the "emotionMenu" folder somewhere you'll remember on your Raspberry Pi
- From here, you can either run the Python script directly from the terminal via "python3 emotionMenu.py", or add it to the end of .bashrc so that it automatically starts on login, like so!
```
# emotionMenu Launcher
if [ -z "$DISPLAY" ] && [ "$(tty)" = "/dev/tty1" ]; then
    # Set this to the directory you've extracted emotionMenu to!
    cd /home/pi/emotionMenu/
    # Launch the menu
    python3 emotionMenu.py
fi
```

## FAQ
- "Does this work on HDTVs?"
Maybe? Probably not. Most resolution content is hardcoded for a 480p/480i resolution, as this is specifically targetting CRT setups. If I ever unravel that thread, I'll remove this section.
- "How do I add/modify shortcuts?"
Open "emotionMenu.py" in your favourite text editor, look for the default launcher items (emulationStation being #1), and add/modify contents to your heart's desire! You can add as many shortcuts as you care to scroll through.
