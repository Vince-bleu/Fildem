# Fildem

## Global menu for Ubuntu 20

[![Buy Me A Coffee](https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg)](https://buymeacoffee.com/gonza)

![Fildem](https://user-images.githubusercontent.com/19943481/95288612-1d272a80-083f-11eb-9400-be88f61e054d.png)

This project is a fork of gnomehud with the adition of a global menu bar. To install it you have to download this repo and install the extension copying/moving the `fildemGMenu@gonza.com` folder into `~/.local/share/gnome-shell/extensions`. Then, you have to run the app with `./run.sh`.

You can also bring a HUD menu with Alt + Space.

This is a prototype, as I don’t know if people will like or how much it will last until devs nuke it, so fell free to let me know your opinion.

## Dependencies

The dependencies are the same as gnome-hud. You can install it with:

```
sudo apt install libbamf3-dev bamfdaemon libkeybinder-3.0-dev
pip3 install fuzzysearch
```

## Install modules for the menu

### Ubuntu 20

You can install the modules with

```
sudo apt install unity-gtk2-module unity-gtk3-module appmenu-gtk3-module
```

And the configure the following files:

- Create the file `~/.gtkrc-2.0` and append `gtk-modules="appmenu-gtk-module"`
- The file `~/.config/gtk-3.0/settings.ini` should have the line `gtk-modules="appmenu-gtk-module"` under [Settings]. If it doesn’t exist create it and paste the following

```
[Settings]
gtk-modules="appmenu-gtk-module"
```

## Customization

### Menu always visible

If you don’t want to have to hover the menu to view it, change `FORCE_SHOW_MENU` in `extension.js` to `true`, and reload the shell (Alt+F2, r).

### Remove space in between buttons

In some gnome themes, the buttons have a small spacing beetween them. This can make the buttons easy to miss and unfocusing our window if it’s not maximized. To fix this, add this somewhere on your `gnome-shell.css` theme:

```
#panel #panelLeft {
  spacing: 0px; }
#panel #panelLeft .panel-button {
  spacing: 0px; }
```
