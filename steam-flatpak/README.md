# steam-flatpak
# Allow Steam flatpak to create game icons in desktop or applications
Allow Steam flatpak to read/write to: ```xdg-desktop``` ```xdg-data/applications``` ```xdg-data/icons```
```
flatpak --user override --filesystem=xdg-data/icons com.valvesoftware.Steam
flatpak --user override --filesystem=xdg-data/applications com.valvesoftware.Steam
flatpak --user override --filesystem=xdg-desktop com.valvesoftware.Steam
```
Put the wrapper script named ```steam``` to your ```$PATH```(like```~/.local/bin```)
