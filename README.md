# gamescope-session

A simple script and session file to run Steam on fullscreen in a console-like environment using Gamescope (like the Steam Deck).

## Disclaimer

This script and session were tested and developed on Arch Linux.  
While it should theoretically work on any distribution, it may not.
You can adapt the session file to work with your greeter of choice.

## Dependencies

For this to work properly, you will need the following packages:

- `wayland`
- `gamescope`
- `steam`
- `sddm` (unless you adapt it to another greeter)

## How to Use

### 1. Download the Files

Simply download both files [here](https://github.com/nunessdev/gamescope-session/archive/refs/heads/main.zip).

### 2. Place the Files in Their Folders

- Place `steam-session.sh` somewhere accessible system-wide.  
  For example: `/usr/local/bin/`

- Place `steam-gamescope.desktop` in `/usr/share/wayland-sessions/`  
  or wherever your Wayland sessions folder is located.

### 3. Update the Files

#### Update the `.desktop` File

If you placed `steam-session.sh` somewhere other than the default,  
update the `Exec` line in `steam-gamescope.desktop`:

```
[Desktop Entry]
Name=Steam
Comment=Steam Big Picture via Gamescope
Exec=/your/path/to/steam-session.sh
Type=Application
```

**Default version:**

```
[Desktop Entry]
Name=Steam
Comment=Steam Big Picture via Gamescope
Exec=/usr/local/bin/steam-session.sh
Type=Application
```

#### Update `steam-session.sh` with Your Monitor Specifications

```
exec gamescope -f -w <your-width> -h <your-height> -r <your-refresh-rate> -- steam -tenfoot
```

**Example:**

```
exec gamescope -f -w 2560 -h 1440 -r 180 -- steam -tenfoot
```
