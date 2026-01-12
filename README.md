# Discord Cursor Capture
Adds a visible overlay cursor, so that the Discord App on Linux (Only works with X11) can capture it during screen sharing. Therefore, the cursor can be seen by the other party watching the screen share. 

## Start
### Install Build Dependencies

Ubuntu/Debian
```bash
sudo apt update
sudo apt install -y build-essential git \
  libx11-dev libxcomposite-dev libxdamage-dev libxrender-dev libxfixes-dev libxext-dev
```
Fedora
```bash
sudo dnf install -y gcc make git \
  libX11-devel libXext-devel libXdamage-devel libXrender-devel libXfixes-devel
```
### Clone the Repo and Build
```bash
git clone https://github.com/yunusdmrl/discord-cursor-capture.git
cd discord-cursor-capture
make
```
### Install the Binary (System-wide)
```bash
sudo make install
```
### Run
```bash
$PATH/find-cursor --cursor-shape --repeat 0 --follow --size 44 --offset 34 -c "#202020" -o 2 -O "#FFFFFF"
```
Change --size and --offset accordingly to your cursor.

Press `Ctrl+C` to stop.

## Notes
- Opaque cursor rendering (solid colour, defaults to black).
- Signal-safe cleanup on `Ctrl+C` to avoid cursor residue.
- Use `-c <color>` to set a different solid cursor colour.

## Credits
Based on [find-cursor](https://github.com/arp242/find-cursor) by Martin Tournoij (arp242), MIT licensed.
This fork focuses on Discord capture usability and cleanup fixes.
