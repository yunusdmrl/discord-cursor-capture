# Discord Cursor Capture

Creates an overlay pointer so that the Discord app on Linux (X11 only) can capture it during screen sharing.

Discord on Linux doesn't capture the actual cursor during screen sharing. This tool draws a cursor overlay that Discord can see and share.

## Installation

Compile with `make`, install with `make install`.

### Dependencies

**Ubuntu/Debian:**
```bash
sudo apt install libx11-dev libxcomposite-dev libxdamage-dev libxrender-dev libxfixes-dev libxext-dev
```

**Fedora:**
```bash
sudo dnf install libX11-devel libXext-devel libXdamage-devel libXrender-devel libXfixes-devel
```

## Usage

```bash
find-cursor --cursor-shape --repeat 0 --follow --size 70 --offset 35
```

This draws your actual cursor shape as an overlay that follows your mouse. Press `Ctrl+C` to stop cleanly.

See `find-cursor -h` for all options.

## Toggle Script

```bash
#!/bin/sh
if pgrep find-cursor; then
    pkill find-cursor
else
    find-cursor --cursor-shape --repeat 0 --follow --size 70 --offset 35 &
fi
```

## Credits

Based on [find-cursor](https://github.com/arp242/find-cursor) by Martin Tournoij (arp242), licensed under MIT.

Modifications:
- Fixed signal handler for clean X11 cleanup on Ctrl+C (prevents cursor residue)
