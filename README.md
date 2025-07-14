# July-14-sway-labwc-desktops-for-slackware64current-update
slackware64  current has labwc in it. It is is pretty trivial to make additions to use it  a stand alone desktop, and also sway

Wlroots, scdoc, labwc, & seatd are now all part of slackware current. Howver, labwc is not superuseful as a standalone desktop in current at this time as: 
out of the box,using the included labwc startup command "labwc",  there is no panel to minimize apps to, no wallpaper setter, no sound suport on startup , no automount on start up.
I have included two trivial slackbuilds for the software packages sfwbar and swaybg which inconjunction with a one line bash startup script and a minimal configuration file adrees the above shortcomings.
The slackbuilds were tested on a vanilla slackware64-current changeroot (default all packages installion ) date of 07-14-2025.
There are no additional deps not included in slackware64-current on that date.
Adding a one line start up script  "startlabwc" "dbus-launch labwc -C ~/.config/labw" and placing a minimal configuration in the ~/.config/labwc folder can fix this. Using dbus-launch enables automount. I specify aa non-default config directory, so that startxfce4 --wayland which uses the default labwc config directory ( ~/.config/labwc ) is not interfered with. The most imporatnt thing to place in the ~/.config/labw directory is an autostart file will call pulseaudio -D to start sound, and swaybg to set wall paper , and sfwbar which provides a pretty taskbar that you can minimize apps to, and a good autocfigured app menu/launcher ( all in its default configuration out of the box). 


Adding sway as an additional deasktop at this point if the above is done is trivial. I offer a slackbuild and config file to place in ~/.config/sway and recomend installation of bemenu from SBo as a app launcher.
