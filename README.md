# Card Wars releases

Card Wars is a turn-based tactics card game by Khan Studios: two knights, one board, thirty-eight cards. Play against the computer or a friend on the same screen.

**Get the game on itch.io: https://khanstudios.itch.io/cards-wars**

This repo only holds the Windows installers and the signed file the game's updater reads. The game's source code is not here.

## Download

- **Latest installer:** [Releases page](https://github.com/Khan-Doruk/card-wars-releases/releases/latest) (`CardWars_Setup_<version>.exe`)
- **Or use itch.io:** the page above has the same installer, and the itch app keeps the game updated for you.

Windows may say "Windows protected your PC" the first time, because the installer isn't code-signed yet. Click **More info**, then **Run anyway**.

## How the in-game updater uses this repo

Every release has three files:

| File | What it is |
|---|---|
| `CardWars_Setup_<version>.exe` | The installer. |
| `latest.json` | The version, the installer's address, its size and its SHA-256. |
| `latest.json.sig` | A signature of `latest.json` made with the Khan Studios update key. |

From version 1.15, an installed copy of the game finds the newest release here. It checks the signature with the public key built into the game, downloads the installer, and checks its size and SHA-256. Only then does it install the update. If any check fails, the download is deleted, nothing is installed, and the game offers the itch.io page instead.

The files sit on the Releases page, not in the repo itself, so each version keeps its own download and the newest one always has the same address.

Made by [Khan Studios](https://khanstudios.itch.io/).
