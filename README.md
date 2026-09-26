# Future RO

A Ragnarok Online server that travels through the game's history: it starts at **Episode 1
(2002)** and moves forward one episode at a time, with the maps, monsters, classes and rules
of each era. Play on the main server with friends, or run your own **solo server** on your PC.

This repository holds the **player downloads**: the Future RO files, the setup, the patcher
and the solo server. The game itself runs on the Ragnarok client from 16 July 2025, which you
get for free with WARPGATE.

## Install in three steps

1. **Get the Ragnarok client with WARPGATE.** Free, 3.8 GB, about 15 minutes.
   Step by step, with pictures: **[Get the client](docs/GET-THE-CLIENT.md)**
2. **Download Future RO** from the [latest release](https://github.com/silkhelp-wq/Future-RO-Client/releases/latest):

   | Your computer | Download | Then |
   |---|---|---|
   | Windows 10 / 11 | `FutureRO-Setup-<version>.exe` | Run it and pick your WARPGATE folder. [Details](docs/WINDOWS.md) |
   | Windows, by hand | `FutureRO-<version>-files.zip` | Extract into your WARPGATE folder, run **Set up Future RO** |
   | Linux | `FutureRO-<version>-linux.tar.gz` | Unpack, run `./install.sh`. It can run WARPGATE for you. [Details](docs/LINUX.md) |
   | macOS (untested) | `FutureRO-<version>-macos.tar.gz` | Unpack, run `./install.sh`. [Details](docs/MACOS.md) |

3. **Play.** The **Future RO** icon checks for updates, then starts the game. **Future RO
   solo** starts your own server first (it needs Docker Desktop, free).

Already have the 2025-07-16 client from WARPGATE? Skip step 1: the setup checks your folder
and only adds what Future RO needs.

## Updates

You never download Future RO again for an update:

- **Game files** update by themselves: the **Future RO** icon checks for patches every time
  you start it (from GitHub, so no Tailscale needed).
- **Your solo server** checks for a newer version when you start it and asks first: **Update
  now**, **Later** or **Skip this version**. Your characters are copied before every update,
  and **Undo the last solo server update** puts everything back.
- **The main server** is updated by us. Nothing to do on your side.

More in [Updates and problem reports](docs/UPDATES-AND-REPORTS.md).

## When something breaks

When an update or the solo server fails, Future RO offers to send a **problem report**. It
shows you the whole report first (versions, your system, the logs; no passwords, your
Windows user name and PC name taken out), and nothing is sent unless you click **Send
report**. You can also send one any time: Start menu -> Future RO -> **Report a problem**
(Linux/macOS: `futurero report`).

Reports go to our server, which turns them into [issues here](https://github.com/silkhelp-wq/Future-RO-Client/issues).
If our server can't be reached, the report opens here as a new issue, already filled in.

## Playing on the main server

The main server is on a private network (Tailscale, free). Set it up once:
[Connecting to the main server](docs/CONNECTING.md). You don't need it to play solo.

---

The server code lives in a separate, private repository. What is here: the Future RO
client files (translation, settings, a patched 2025-07-16 game program), the setup and
launcher scripts, and the solo server image. Ragnarok Online is a trademark of Gravity Co.,
Ltd.; Future RO is a fan project and not affiliated with Gravity.
