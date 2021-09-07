# Themes for Zorin OS by REV3NT3CH

These themes fully apply to Grub, Plymouth Bootanimation, GDM login screen, Desktop Environment and Icons for Zorin Core 17.x

For basic instruction I have used R3VR3D as the default example in some of the commands used below. Change the commands with R3VR3D to the name of the theme you want to apply when neccessary.

**To get started lets open a new Terminal and enter the following commands:**

## Dependencies & Prerequisites

```
sudo apt-get install python3-lxml libglib2.0-dev dconf-cli git
```
```
git clone git@github.com:REV3NT3CH/ZorinThemes.git && git clone --depth=1 https://github.com/realmazharhussain/gdm-tools.git && git clone https://github.com/worron/ACYLS.git ~/.icons/ACYLS
```

## Place themes in respectable folders

```
sudo cp -R ~/ZorinThemes/themes /usr/share && sudo cp -R ~/ZorinThemes/grub/themes /usr/share/grub && sudo cp -R ~/ZorinThemes/plymouth/themes /usr/share/plymouth && cp -R ~/ZorinThemes/wallpapers ~/Pictures && cp ~/.icons/ACYLS/desktop/acyls.desktop ~/.local/share/applications
```

## Set Desktop wallpaper

```
gsettings set org.gnome.desktop.background picture-uri ~/Pictures/wallpapers/R3VR3D/background.png
```

## Set the theme & background of gdm3 login screen

```
cd gdm-tools
```
```
./install.sh
```
```
set-gdm-theme backup update
```
```
set-gdm-theme set R3VR3D
```
```
set-gdm-theme set -b ~/Pictures/wallpapers/R3VR3D/background.png
```

## Set up the icons to match the theme

cd back to the home directory before entering next command:

```
python3 ~/.icons/ACYLS/scripts/run.py
```

At this point you can then set and apply the colors and designs for the icons (Theme colors below):

- 0RCH1D: #6494EE
- B0B4ZUL: #00FFF5
- N4710N: #C0C0C0
- PURPL3: #800080
- R3VR3D: #DC0000
- T0X1C: #00C850

Once finished selecting the styles and colors you can now close out of this program.

## Update Grub & Bootanimation to match theme
```
sudo sed -i 's|GRUB_THEME=/usr/share/grub/themes/zorin/theme.txt|GRUB_THEME=/usr/share/grub/themes/R3VR3D/theme.txt|' /etc/default/grub
```
```
sudo cp -R ~/ZorinThemes/plymouth/images/R3VR3D/* /usr/share/plymouth
```
```
sudo update-grub && sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/0RCH1D/0RCH1D.plymouth 100 && sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/B0B4ZUL/B0B4ZUL.plymouth 100 && sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/N4710N/N4710N.plymouth 100 && sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/PURPL3/PURPL3.plymouth 100 && sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/R3VR3D/R3VR3D.plymouth 100 && sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/T0X1C/T0X1C.plymouth 100
```
```
sudo update-alternatives --config default.plymouth
```
After running the above command select the number associated with the theme you want:
```
sudo update-initramfs -u
```

## Set Desktop Theme & Icons universally in the following location

Zorin Appearance > Themes > Other.

## Screenshots

Screenshots can be found <a href="https://github.com/REV3NT3CH/ZorinThemes/blob/master/screenshots/screenshots.md">here</a>

## Credits & Thanks
Credits to the Zorin team for the ZorinGrey-Dark theme, Grub theme and Plymouth theme I based this off of found here https://github.com/ZorinOS/zorin-desktop-themes 

Credits to realmazharhussain for the gdm tools used in the instructions and can be found here https://github.com/realmazharhussain/gdm-tools

Credits to worron for his work and contributions to ACYLS icons that are used in the instructions and found here https://github.com/worron/ACYLS

Credits to mystica-264 on deviantart for the dual hexagon pattern used in the wallpapers

Huge THANK YOU to the open-source community for all the amazing projects we create and achieve.
