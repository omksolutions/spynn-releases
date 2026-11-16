# Spynn

A 5 v 5 physics football game for Windows: play against the computer, with friends over a network, or with several controllers at one PC.

Downloads are on the [Releases](../../releases) page, the newest at the top. The two versions below are separate games: 0.1 and 0.2 can't play together.

---

## Version 0.3 (new)

A rebuild on DirectX 12, with a main menu, match setup, hosting and joining from the menus, and up to ten people in a match.

### Requirements

- Windows 10 (version 1909 or later) or Windows 11, 64-bit.
- A DirectX 12 graphics card with a current driver, with Shader Model 6.6, which most cards of the last several years have, Intel's built-in graphics included. If yours falls short, the game says what is missing. Updating the graphics driver is what most often fixes it: from Intel, NVIDIA or AMD, or on a Surface or similar laptop through Windows Update (including its optional updates).
- Built-in graphics will run it, but slower than a graphics card: on a laptop with both, it uses the faster.
- A keyboard, or a controller (Xbox-style). A controller is no longer required.

### Getting started

1. Download `Spynn.zip` from the 0.2 release and **unzip it**. Run `Spynn.exe` from the unzipped folder, not from inside the zip. Nothing needs installing.
2. Windows may say it protected your PC from an unrecognised app, because the game isn't signed: choose **More info**, then **Run anyway**. Some antivirus programs may flag it for the same reason.
3. The game opens fullscreen. **Alt+Enter** or **F11** switches to a window and back.

### Controls

| | Keyboard | Controller |
|---|---|---|
| Move | W A S D or the arrow keys | Left stick |
| Boost | Shift or Space | A |
| Pause | Escape | |

The menus use the keyboard (arrow keys, Enter, Escape, Tab) or the mouse.

### Playing against the computer

Choose **Play**, then set up the match:

- **Your name**: shown over your player.
- **Match length**: 3, 5, 10, 15, 20 or 30 minutes, or 1 hour.
- **Computer**: Easy, Normal or Hard.
- **Your team**: Red or Blue.

Up and Down move between rows, Left and Right change a value, Enter starts.

### Playing together over a network

**To host:** choose **Host a match**, set it up as above, and Start. The port is 7777 unless you change it; add a password if you want a private match. When Windows asks whether to let the game through its firewall, allow it (on private networks at least).

Then press Escape: the pause menu shows where friends join.

- **On this network**: the address for anyone on the same Wi-Fi or local network.
- **Over the internet**: shown once your router has opened the port by itself. If it can't, forward UDP port 7777 to the hosting PC in your router's settings, and friends join at your public address.

**To join:** choose **Join a match**, type the host's address (and the port, and password if there is one), your name, and Join. The line under the boxes says how it went.

A match holds up to ten people; the computer plays every seat nobody has. If someone drops out, the computer plays for them until they rejoin. A match with others in it carries on while you're paused.

### Several players at one PC

In a match you started or are hosting, anyone with another controller presses **Start** to take a player of their own, and **Back** to give it up. The first to join plays on your team, whoever joins after on the other. Each player gets a ring of their own colour. Up to four controllers are supported. (This isn't available when you've joined someone else's match: that's one player per PC.)

### The server (optional)

`SpynnServer.exe`, in the same folder, hosts a match with no window, for a PC that only hosts. Run it from a command prompt in that folder; everyone, including you, then joins it with **Join a match**. Ctrl+C stops it.

- `--at <port>` where it listens (7777 unless told), or `--at <address:port>` for one address of the PC only.
- `--ai <easy | normal | hard>` how well the computer plays; two levels, as in `--ai "easy hard"`, for each team.
- `--password <word>` a private match.
- `--seed <number>` a different match.

The server doesn't ask the router to open its port: for play over the internet, forward UDP port 7777 by hand. Its matches last 10 minutes (`matchSeconds` in `assets\Data\Balance.json`).

### Known issues

- This is an early demo: expect bugs.
- There is no sound yet.
- Controllers can't move through the menus yet; use the keyboard or mouse there.
- Your name isn't remembered between runs, and there's no settings screen yet.
- At full time the match stops: press Escape, then Leave match.

### If something goes wrong

`spynn.log` in the game's folder says what happened (it's rewritten each run). Send it along with a description of what you did.

---

## Version 0.1 (old)

The original version, built on OpenGL 4.6 / GLSL, using DirectX XInput for gamepad input. It comes as two programs, a server and a client.

### Quick setup

1. Run `SpynnServer.exe` and note the hostname or local IP.
2. Connect a gamepad (an Xbox controller is ideal, but most should work).
3. Run `SpynnClient.exe`, the main game client.
4. Type the server's IP or hostname into the **Server address** field (click the box; it highlights slightly, and typing overwrites what is there).
5. Press **C** or click **Connect**.
6. Once connected you'll see your player's sphere on screen and can kick the ball around.
7. Get another player to connect: the server assigns players to the two teams in turn.

The score and time limits are set in the server's `server-config.json`; restart the server after changing it.

**Note:** the game isn't finished and probably has many bugs. It may not play well on a slow network, as the physics is real-time.

### Requirements

- Windows only.
- A graphics card capable of OpenGL 4.6.
- A working PC-compatible gamepad.
- Click **Allow** if Windows asks for a firewall entry.
