## How To Install

#### Installation steps for common desktop environments that use compositing effects:

Step 1: Create ".themes" and ".icons" directories  in your user directory "/home/$USER/" if they don't already exist.
(Note: You may have to enable "view hidden folders" in the file manager to see ".themes" and ".icons" after creating them.)

Step 2: Copy the "Chicago95-custom" directory into ".themes".

Step 3: Copy the "Chicago95-icons-tux" directory into ".icons".

Step 4: Copy the "gtk.css" file from the "misc" directory into "/home/$USER/.config/gtk-3.0/".
(Note: You may have to create the "gtk-3.0" directory if it's not there.)

Log out then log back in.

Finished!

#### Installation steps for non-compositing desktop environments:

Step 1: Create ".themes" and ".icons" directories  in your user directory "/home/$USER/" if they don't already exist.
(Note: You may have to enable "view hidden folders" in the file manager to see ".themes" and ".icons" after creating them.)

Step 2: Copy the "Chicago95-custom (no_comp)" directory into ".themes".

Step 3: Copy the "Chicago95-icons-tux" directory into ".icons".

Step 4: Copy the "gtk.css" file from the "misc/no_comp" directory into "/home/$USER/.config/gtk-3.0/".
(Note: You may have to create the "gtk-3.0" directory if it's not there.)

Step 5: Copy the ".xsessionrc" file from the "misc/no_comp" directory into your user directory "/home/$USER/".

Step 6: Install gtk3-nocsd. Note: gtk3-nocsd is available in the main Ubuntu repository, but is out of date and won't function for some GTK3 applications, so we'll install it from source as seen from the following steps:

Download the repo and extract it:

    wget https://github.com/PCMan/gtk3-nocsd/archive/master.zip
    unzip master.zip

Install dependencies:

    sudo apt install pkg-config libgtk-3-dev libgirepository1.0-dev

Move to gtk3-nocsd directory and build the application:

    cd gtk3-nocsd-master/
    make

Move the newly compiled executable file and library.

    sudo cp libgtk3-nocsd.so.0 /usr/lib/x86_64-linux-gnu/
    sudo cp gtk3-nocsd /usr/bin/

Log out then log back in.

Finished!

Note: The ".xsessionrc" file is required for running gtk3-nocsd upon login. If you didn't copy the file into the "/home/$USER/" directory, GTK3+ applications won't display menu borders and header bars will appear distorted.

## Configuration
Enable the notification balloon theme. Open the system notification settings manager (xfce4-notifyd-config) and in the "Theme" option select Chicago95-custom in the pull down menu.

Enable the shell theme. Open the system appearance settings manager (xfce4-appearance-settings) and in the "Style" tab select "Chicago95-custom."

Enable the window manager theme. Open the XFCE Window Manager settings (xfwm4-settings) and in the "Style" tab select "Chicago95-custom."

#### • Font Settings:
In the XFCE Appearance Manager, select the "Fonts" tab and apply the following information.

    Default Font: Sans 10

    Enable Antialiasing: Yes

    Hinting: Full

    Sub-pixel order: None

In the XFCE Window Manager

    Title bar font: Sans Bold 8pt

#### • Compositor Settings:
In the XFCE "Window Manager Tweaks" manager, select the "Compositor" tab. Uncheck "Show shadows under dock windows." This will prevent applications from casting a shadow onto the task bar.

Note: If you disable the compositor at anytime, GTK3 application menu borders will cease to render. Look at the install steps for setting up this theme for non-compositing environments.

#### • Panel Setup:
Create a new panel if necessary. Horizontal, 32px high ONLY, and 100% Length. In the “Appearance” tab set the background style to "None" so that it inherits the theme style. (Only horizontal taskbar. No vertical taskbar, sorry. I'll try adjusting the theme for vertical bars as an option eventually.)

In the “Items” tab, add the following in this order:

    1. Application Menu OR Whisker Menu; 

    2. Separator (Handle Style); 

    3. Custom Launcher, Custom Launcher, Custom Launcher, etc.

    4. “Show Desktop” plugin; 

    5. Separator (Handle Style); 

    6. Window Buttons (Sorting Order: Time-stamp and Window Grouping is Always. Uncheck “Show Handle” if it’s enabled.); 

    7. Separator (Transparent with Expanding); 

    8. Separator (Handle Style); 

    9. Notification Area (19px max icon size); 

    10. PulseAudio Plugin (Uncheck mark in the plugin settings, "Show Notifications when volume changes." it will conflict with XFCE notifiyd by making duplicate volume notifications); 

    11. Separator (Transparent); 

    12. Orage Panel Clock. ( In the plugin settings, enable check box “Show frame” and replace the text in “Line 1” with %I:%M %p.) Note: If you want to display the date in the clock, append “%D” in “Line 1.” If you want a better looking date, you could replace that by appending “%b %m %Y” instead.

#### • Whisker Menu / Application Menu start button:
Open the properties menu of either Whisker Menu or Application Menu by right clicking on their panel icons and selecting “properties.” Click the icon button in the properties window. 

The custom Start Button icons are located in the following directory (depending on where you installed the overall theme): /home/$USER/.themes/Chicago95-custom/misc/GTK3 start buttons/. Select the file “start-button_windows” or “start-button_tux.”

If the icon appears crunched or blurry, then log out and log back in. The icon should appear a regular size.

#### • Libre Office 5 GTK3 workaround:
IF you are seeing issues with Libre Office 5 incorrectly rendering menu items, borders, and boxes. As a workaround you can remove the libreoffice-gtk3 package. This will cause Libre Office to fallback into GTK2, which is functioning properly.

    sudo apt remove libreoffice-gtk3

## Extra Stuff:
If you want to install the mouse cursor theme, lightdm theme, Plymouth theme, these are available at [https://github.com/grassmunk/Chicago95](https://github.com/grassmunk/Chicago95). Follow the guides there if you want these!
