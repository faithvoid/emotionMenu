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
- "How do I change the background video / text colour / font?"
Great question! These are all values that are modifiable in emotionMenu.py, so you can set it up to your liking! By default, it comes themed to look like the Playstation 2's iconic main menu, but you're free to make any changes you see fit to your setup!
- "Why make this in Python/PyGame instead of C++ / SDL?"
Python's the language I'm most fluent in and PyGame + python-av run wonderfully in terminal sessions, simple as that. C++ and SDL would be a better choice for performance and stability, but that also involves porting binaries to different platforms and whatnot, whereas this frontend can be modified to run on just about anything that runs Python and takes *nix commands.

## TODO
[_] Add custom theme support
[_] Add "Settings" menu and associated .cfg file
[_] Remove resolution-specific code at some point down the line
