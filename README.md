# Discord Cursor Capture
Adds a visible overlay cursor so Discord on Linux/X11 can capture it during screen sharing.

## Quick start
```bash
make
sudo make install    # installs /usr/local/bin/find-cursor
find-cursor --cursor-shape --repeat 0 --follow --size 70 --offset 35
```
Press `Ctrl+C` to stop; cleanup is now handled safely.

### Handy alias (bash)
```bash
echo "alias dcursor='find-cursor --cursor-shape --repeat 0 --follow --size 70 --offset 35'" >> ~/.bashrc
source ~/.bashrc
```

## Dependencies
- Ubuntu/Debian: `sudo apt install libx11-dev libxcomposite-dev libxdamage-dev libxrender-dev libxfixes-dev libxext-dev`
- Fedora: `sudo dnf install libX11-devel libXext-devel libXdamage-devel libXrender-devel libXfixes-devel`

## Notes
- Opaque cursor rendering (solid color, defaults to black).
- Signal-safe cleanup on `Ctrl+C` to avoid residue windows.
- Use `-c <color>` to set a different solid cursor color.

## Credits
Based on [find-cursor](https://github.com/arp242/find-cursor) by Martin Tournoij (arp242), MIT licensed.
This fork focuses on Discord capture usability and cleanup fixes.
