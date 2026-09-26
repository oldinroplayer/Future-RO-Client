# Updates and problem reports

## What updates, and how

| What | How it updates | You see |
|---|---|---|
| **Game files** (translation, settings, the game program, the launcher scripts) | The patcher, every time you start **Future RO** (or **Future RO solo**) | The patcher window: *Checking for updates...*, then **Play** |
| **Your solo server** | The solo launcher checks when you start **Future RO solo** | A question: **Update now** / **Later** / **Skip this version** |
| **The main server** | We update it | Nothing (sometimes a game-file update comes with it) |
| **The patcher itself, Microsoft runtimes** | Only with a new setup, rarely | A note in the release |

### Game files (patches)

The patcher downloads patches from this repository (the
[patches](https://github.com/silkhelp-wq/Future-RO-Client/releases/tag/patches) release),
and from the Future RO server if GitHub can't be reached. Each patch holds only the files that
changed, usually a few kilobytes. If there's no internet, **Play anyway** starts the game
you have.

Linux and macOS: `futurero play` and `futurero solo` install patches first; `futurero update`
does only that.

### Your solo server

When a new solo server is out, **Future RO solo** asks before it starts:

- **Update now** downloads it (130 MB or so) and checks it. It then **saves a copy of your
  characters**, installs the new server and starts it.
- **Later** plays on the version you have and asks again next time.
- **Skip this version** stops asking about that one version (the next one asks again).

Check any time: Start menu -> Future RO -> **Check for solo server updates**
(Linux/macOS: `futurero server update`).

**If the new version doesn't work**, the launcher offers to go back right away. Later, use
Start menu -> Future RO -> **Undo the last solo server update** (Linux/macOS:
`futurero server rollback`). That puts back the previous server **and your characters as
they were before the update**. Anything played on the new version is lost, so it asks first.

## Problem reports

Future RO offers a report when an update fails, the solo server doesn't start, or you open
**Report a problem** yourself.

**What's in a report** (you see all of it before sending):

- what went wrong, and what you type in the box (optional)
- Future RO versions (game-file patch number, solo server version)
- your system: Windows version (or Linux distribution / macOS version), graphics card and
  driver, memory, free disk space
- whether any Future RO files are missing or changed
- the last lines of the solo launcher's and the solo server's logs

**What's not in it:** passwords, chat, your characters. Your Windows user name, PC name and
e-mail addresses are replaced by `<user>`, `<pc>` and `<email>` before you see the report.

**Where it goes:** to the Future RO server, which files it as an
[issue in this repository](https://github.com/silkhelp-wq/Future-RO-Client/issues)
(public, so anyone can read it). If our server can't be reached (for example without
Tailscale), your browser opens a new GitHub issue with the report filled in. Click
**Create** there to send it (a free GitHub account is needed), or close it to not send it.
Every report is also saved on your PC: `logs\report-<date>.txt` in the game folder
(Linux/macOS: `~/FutureRO/logs/`).
