# Doom-Emacs-Wayland


## 1. Install the Emacs (Wayland) Package, provided by your package manager

```bash
sudo pacman -Syy emacs-wayland
```

## 2. Follow the Doom Emacs Installation Process:

```bash
git clone --depth 1 https://github.com/doomemacs/doomemacs ~/.config/emacs
~/.config/emacs/bin/doom install
```

## 3. Add Doom Emacs to your PATH:

e.g: On fish
```bash
fish_add_path /home/sohighman/.emacs.d/bin
```

## 4. Run ``doom sync`` and ``doom doctor``

## 5. Create Custom Desktop Entries for launching a Server & Client:

- The correct command for launching a Daemon on Wayland is:
``emacs --fg-daemon``
- And to connect to the server:
``emacsclient -c``

## Server Entry:
(Note: Use your preferred notification daemon, I am using ``mako``)
```bash
[Desktop Entry]
Type=Application
Name=Doom Emacs (Daemon)
Comment=A configuration framework for GNU Emacs
Exec=systemd-run --user --scope /bin/bash -c "/usr/bin/emacs --fg-daemon & notify-send -i /home/sohighman/.local/share/doom/doom-demon.png 'Demon Running! 👹'"
Icon=/home/sohighman/.local/share/doom/doom-demon.png
Categories=Development;TextEditor;
Keywords=emacs;doom;editor;text;programming;development;
Terminal=false
```
## Client Desktop Entries:

```bash
[Desktop Entry]
Type=Application
Name=Doom Emacs (Client)
Comment=A configuration framework for GNU Emacs
Exec=/usr/bin/emacsclient -c 
Icon=/home/sohighman/.local/share/doom/cacodemon_sprite.png
Categories=Development;TextEditor;
Keywords=emacs;doom;editor;text;programming;development;
Terminal=false
```

## 6. Save your desktop entries.
- My recommendation is to save them under ``.local/share/applications``
- Don't forget to add Read & Write permissions to your desktop entries, for e.g:
``chmod +x doom-emacs-client.desktop``
