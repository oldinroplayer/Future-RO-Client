# Future RO on macOS

## Install

1. Download `FutureRO-<version>-macos.tar.gz` from the latest release:
   https://github.com/silkhelp-wq/Future-RO-Client/releases/latest
2. Open **Terminal** (Launchpad -> Other -> Terminal), unpack the download there and start the
   installer. Not by double-clicking in Finder: the installer asks questions, and files
   unpacked by Finder may be refused when run.

       cd ~/Downloads
       tar xzf FutureRO-*-macos.tar.gz
       cd FutureRO-*-macos
       bash install.sh

   Install into another folder than the unpacked download.
3. Answer its questions. It shows what it is about to do and asks first:
   - **Folder**: press Enter for `~/Applications/FutureRO`, or type another folder or drive.
   - **Developer tools**: if your Mac has no `python3` yet, the installer offers Apple's
     command line developer tools (`xcode-select --install`: click **Install** in the window
     that opens; a few minutes, no Xcode needed).
   - **Rosetta 2** (Apple silicon, M1 and later): Wine and the solo server are built for
     Intel Macs, so the installer asks to install Rosetta 2, Apple's translator for them.
   - **Wine** runs the Windows game. It is downloaded for you (Wine Staging built by Gcenx,
     about 190 MB, into ~/Applications; Homebrew no longer offers Wine). A Wine app you
     already have in Applications is used as it is.
   - **OrbStack** runs the solo server. It is downloaded for you (free for personal use,
     about 460 MB) unless you already have OrbStack or Docker Desktop; then it opens and the
     installer waits until it runs. The first time, OrbStack asks a few things in its own
     window: pick **Docker** and allow its helper with your Mac password. OrbStack needs
     macOS 14 or newer; on an older Mac say no, install Docker Desktop yourself, open it once
     and run `bash install.sh` again.
   - **Your Ragnarok client**: Future RO goes on top of WARPGATE's "WARP0716 Full Client
     2025-07-16" (free, 3.8 GB). WARPGATE is a Windows program and its window crashes under
     Wine on a Mac, so download the client on a Windows or Linux PC, copy the folder to your
     Mac, then choose **2** and type its folder. The guide shows how:
     https://github.com/silkhelp-wq/Future-RO-Client/blob/main/docs/GET-THE-CLIENT.md
   - **Main server address**: the address of the Future RO main server, handed out in the
     Future RO Discord (https://discord.gg/gSwM9t8Dcx). Press Enter to add it later (`futurero address`).
   - **Solo server**: say yes to play on your own Mac too. Said no, or it was skipped? Run
     `bash install.sh` from the download again to add it.
   - **Your solo account**: the name (4-23 letters, digits or _) and password (6-23
     characters) you log in with on the solo server.
4. Start **Future RO** (main server) or **Future RO solo** from Launchpad (the apps are in
   ~/Applications) or from the .command icons on your Desktop. The `futurero` command
   (`futurero play`, `futurero solo`, ...) works in a **new** Terminal window: the installer
   adds it for new windows only. `~/Applications/FutureRO/bin/futurero` always works.

The unpacked download folder can be deleted after installing.

## Playing solo

**Future RO solo** installs new patches, starts your own server (about 30 seconds; the first
start about a minute, and a bit longer through Rosetta on Apple silicon; a notification says
when it is ready), then the game, already pointed at your own server - just log in. When you
close the game the server saves and stops, so nothing keeps running.

The solo server on macOS is new: we have not run it on a real Mac yet. If it does not start,
`futurero report` tells us what happened (you see the report first, and nothing is sent
without your OK).

- `futurero server status` / `futurero server logs`: is it running, and what it says.
- `futurero account NAME PASSWORD` makes another account (`gm` at the end for a GM one). It
  starts the solo server for a moment if it is not running.
- In the game's server list pick **Future RO solo (this PC)**. The list shows one server at a
  time: **Future RO** starts the game pointed at the main server, **Future RO solo** at yours.
- Your solo characters live in Docker's own storage, the volume `futurero-solo-data` (an
  older install that already has a `server-data` folder in the install folder keeps using it).
  Removing the Docker volume, or OrbStack's / Docker Desktop's "reset" or "Clean / Purge data",
  deletes them.

## Playing on the main server

Needs Tailscale (see below). **Future RO** installs new patches first, then starts the game;
pick **Future RO** in the server list. Tailscale's own command lives inside its app:
`/Applications/Tailscale.app/Contents/MacOS/Tailscale` (the connecting guide uses it).

## Updates and problems

- `futurero play` / `futurero solo` install game-file updates first (from GitHub, or from the
  main server once you have entered its address).
- `futurero solo` asks when a newer solo server is out (update now / later / skip this
  version) and keeps a copy of your characters first; `futurero server rollback` goes back.
  `futurero server update` checks now.
- `futurero report` sends us a problem report. It shows you everything in it first and asks.
  The launcher also offers one when something fails.
- `futurero check` says whether the client and the Future RO files are complete;
  `futurero warpgate` opens WARPGATE again (it crashes on the Macs we tried, see above).

## Other

- `futurero setup`: resolution and graphics options.
- `futurero uninstall`: removes Future RO (asks before deleting solo characters). The
  WARPGATE client stays; delete its folder yourself if you don't need it.
