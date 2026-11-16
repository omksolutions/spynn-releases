# Spynn

A 5 v 5 physics football game for Windows: play against the computer, with friends over a network, or with several controllers at one PC.

Downloads are on the [Releases](../../releases) page, the newest at the top. Version 0.1 is the original game; 0.2 and later are a rebuild. Everyone playing together needs the same version.

---

## Version 0.3 (new)

A rebuild on DirectX 12, with a main menu, match setup, hosting and joining from the menus, and up to ten people in a match. New since 0.2: a full-time screen with a rematch, notices of who has come and gone, and a server that starts the next match by itself.

### Requirements

- Windows 10 (version 1909 or later) or Windows 11, 64-bit.
- A DirectX 12 graphics card with a current driver, with Shader Model 6.6, which most cards of the last several years have, Intel's built-in graphics included. If yours falls short, the game says what is missing. Updating the graphics driver is what most often fixes it: from Intel, NVIDIA or AMD, or on a Surface or similar laptop through Windows Update (including its optional updates).
- Built-in graphics will run it, but slower than a graphics card: on a laptop with both, it uses the faster.
- A keyboard, or a controller (Xbox-style).

### Getting started

1. Download `Spynn.zip` from the newest release. **Before unzipping it, unblock it** so Windows doesn't warn about the game: see [Windows protected your PC](#windows-protected-your-pc) below.
2. Unzip it, and run `Spynn.exe` from the unzipped folder, not from inside the zip. Nothing needs installing.
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
- **Match length**: 3, 5, 10, 15, 20 or 30 minutes, or 1 hour. A match also ends when a team scores 5.
- **Computer**: Easy, Normal or Hard.
- **Your team**: Red or Blue.

Up and Down move between rows, Left and Right change a value, Enter starts.

### Playing together over a network

**To host:** choose **Host a match**, set it up as above, and Start. The port is 7777 unless you change it; add a password if you want a private match. When Windows asks whether to let the game through its firewall, allow it (on private networks at least).

Then press Escape: the pause menu shows where friends join.

- **On this network**: the address for anyone on the same Wi-Fi or local network.
- **Over the internet**: shown once your router has opened the port by itself. If it can't, forward UDP port 7777 to the hosting PC in your router's settings, and friends join at your public address.

**To join:** choose **Join a match**, type the host's address (and the port, and password if there is one), your name, and Join. The line under the boxes says how it went.

A match holds up to ten people; the computer plays every seat nobody has. If someone drops out, the computer plays for them until they rejoin, and a notice says who has come and gone. A match with others in it carries on while you're paused.

### At full time

A panel shows the result. **Rematch** plays again from kick-off with the same teams and settings; **Leave match** goes back to the main menu. In someone else's match the host decides on a rematch, and on a server the next match starts by itself after 30 seconds.

### Several players at one PC

In a match you started or are hosting, anyone with another controller presses **Start** to take a player of their own, and **Back** to give it up. The first to join plays on your team, whoever joins after on the other. Each player gets a ring of their own colour. Up to four controllers are supported. (This isn't available when you've joined someone else's match: that's one player per PC.)

### The server (optional)

`SpynnServer.exe`, in the same folder, hosts matches with no window, for a PC that only hosts. Run it from a command prompt in that folder; everyone, including you, then joins it with **Join a match**. Ctrl+C stops it.

- `--at <port>` where it listens (7777 unless told), or `--at <address:port>` for one address of the PC only.
- `--ai <easy | normal | hard>` how well the computer plays; two levels, as in `--ai "easy hard"`, for each team.
- `--password <word>` a private match.
- `--seed <number>` a different match.

The server doesn't ask the router to open its port: for play over the internet, forward UDP port 7777 by hand.

Its matches are set in `assets\Data\Balance.json`, which it reads again before each new match, so you can change them while it runs:

- `matchSeconds`: how long a match lasts (600, ten minutes).
- `goalLimit`: the goals that win it (5; 0 for none).
- `rematchSeconds`: how long after full time the next match starts (30; 0 never to start one).

### Known issues

- This is an early demo: expect bugs.
- There is no sound yet.
- Controllers can't move through the menus yet; use the keyboard or mouse there.
- Your name isn't remembered between runs, and there's no settings screen yet.

### Windows protected your PC

> [!IMPORTANT]
> **Unblock the zip before you unzip it**, and Windows won't warn about the game at all:
>
> 1. Right-click `Spynn.zip` and choose **Properties**.
> 2. On the **General** tab, tick **Unblock** (at the bottom, beside Security) and click **OK**.
> 3. Now unzip it and run `Spynn.exe`.

If you've already unzipped it, Windows says it protected your PC when you run the game: choose **More info**, then **Run anyway**. Or delete the unzipped folder, unblock the zip, and unzip it again.

Why it happens: Windows checks programs downloaded from the internet against publishers it knows. Spynn isn't (yet) signed with a paid certificate, so it shows as an unknown publisher, and every new version starts out unknown. Some antivirus programs may flag it for the same reason; if yours does, add the game's folder to its allowed list.

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
- Some PCs or antivirus programs may wrongly flag the programs as malware; ignore the warning or add them to a safe list if needed.
