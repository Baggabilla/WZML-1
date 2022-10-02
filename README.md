<p align="center">
    <a href="https://github.com/weebzone/WZML">
        <kbd>
            <img width="250" src="https://telegra.ph/file/496644cbabaeb916e3616.png" alt="WeebZone Logo">
        </kbd>
    </a>
</p>

<p align="center">
<div align=center>

[![GitHub forks](https://img.shields.io/github/forks/weebzone/WZML?style=social)](https://github.com/weebzone/WZML/fork)
[![GitHub followers](https://img.shields.io/github/followers/weebzone?style=social&label=weebzone%20Followers)](https://github.com/weebzone)

----

[![](https://img.shields.io/github/repo-size/weebzone/WZML?color=green&label=Repo%20Size&labelColor=292c3b)](#) [![](https://img.shields.io/github/commit-activity/m/weebzone/WZML?logo=github&labelColor=292c3b&label=Github%20Commits)](#) [![](https://img.shields.io/github/license/weebzone/WZML?style=flat&label=License&labelColor=292c3b)](#)|[![](https://img.shields.io/github/issues-raw/weebzone/WZML?style=flat&label=Open%20Issues&labelColor=292c3b)](#) [![](https://img.shields.io/github/issues-closed-raw/weebzone/WZML?style=flat&label=Closed%20Issues&labelColor=292c3b)](#) [![](https://img.shields.io/github/issues-pr-raw/weebzone/WZML?style=flat&label=Open%20Pull%20Requests&labelColor=292c3b)](#) [![](https://img.shields.io/github/issues-pr-closed-raw/weebzone/WZML?style=flat&label=Closed%20Pull%20Requests&labelColor=292c3b)](#)
:---:|:---:|
[![](https://img.shields.io/github/languages/count/weebzone/WZML?style=flat&label=Total%20Languages&labelColor=292c3b&color=blueviolet)](#) [![](https://img.shields.io/github/languages/top/weebzone/WZML?style=flat&logo=python&labelColor=292c3b)](#) [![](https://img.shields.io/github/last-commit/weebzone/WZML?style=flat&label=Last%20Commit&labelColor=292c3b&color=important)](#) [![](https://badgen.net/github/branches/weebzone/WZML?label=Total%20Branches&labelColor=292c3b)](#)|[![](https://img.shields.io/github/forks/weebzone/WZML?style=flat&logo=github&label=Forks&labelColor=292c3b&color=critical)](#) [![](https://img.shields.io/github/stars/weebzone/WZML?style=flat&logo=github&label=Stars&labelColor=292c3b&color=yellow)](#) [![](https://badgen.net/docker/pulls/codewithweeb/weebzone?icon=docker&label=Pulls&labelColor=292c3b&color=blue)](#)
[![](https://img.shields.io/badge/Telegram%20Channel-Join-9cf?style=for-the-badge&logo=telegram&logoColor=blue&style=flat&labelColor=292c3b)](https://t.me/WeebZone_updates) |[![](https://img.shields.io/badge/Support%20Group-Join-9cf?style=for-the-badge&logo=telegram&logoColor=blue&style=flat&labelColor=292c3b)](https://t.me/WeebZ) |

</div>

----

## ***WeebZone MLTB***

<div align=center>

ℹ️ A Powerful Pyrogram Based Telegram Mirror Leech Bot Modded by Codewithweeb to directly Mirror to Google Drive or Leech to Telegram, with Multi Direct Links Support for Enhanced Mirroring & Leeching.|
---|
    
### ***Source Code*** : [Repo](https://github.com/weebzone/WZML)

#### Note: `If you Like My Work, Give Stars ⭐ to the Repo and Follow Me on Github`
    
----
</div>
</p>

### 1. [***Getting Started***](https://github.com/weebzone/WZML/wiki/Getting-Started)
Introduction To the Bot

### 2. [***Features***](https://github.com/weebzone/WZML/wiki/Features)
List of features supported by bot

### 3. [***config.env Variables***](https://github.com/weebzone/WZML/wiki/Setting-up-the-config.env-file)
List of Variables used by the Bot



---
### Deploying on VPS
**NOTE**: If you want to use port other than 80, change it ) also.

## Deploying on VPS Using Docker
- Clone this repo:
```
git clone https://github.com/weebzone/WZML mirrorbot/ && cd mirrorbot
```
- Start Docker daemon (SKIP if already running):
```
sudo dockerd
```
- Build Docker image:
```
sudo docker build . -t mirror-bot
```
- Run the image:
```
sudo docker run -p 80:80 mirror-bot
```


## To stop the image:
```
sudo docker ps
```
##
```
sudo docker stop id
```

## Bot commands to be set in [@BotFather](https://t.me/BotFather)

```
status - Shows a status of all the downloads
speedtest - Speedtest of server
leech - Start leeching to Telegram, Use /leech s to select files before leeching
mirror - Start mirroring to Google Drive.
qbzipmirror - [magnet_link][torrent_file][torrent_file_url] Start mirroring using qBittorrent and upload the file/folder compressed with zip extension
qbmirror - [magnet_link][torrent_file][torrent_file_url] Start Mirroring using qBittorrent
qbmirrors - to select files before downloading
clone - [drive_url][gdtot_url] Copy file/folder to Google Drive
qbleech - [magnet_link][torrent_file][torrent_file_url]  Start leeching to Telegram using qBittorrent, Use 
qbleechs - Qbleech to select files before leeching
qbzipleech - [magnet_link][torrent_file][torrent_file_url] Start leeching to Telegram using qBittorrent and upload the file/folder compressed with zip extension
qbunzipleech - [magnet_link][torrent_file][torrent_file_url] Start leeching to Telegram using qBittorrent and upload the file/folder extracted from any archive extension
prename - Set Prename to leech files
caption - Set Caption for leech files
zipmirror - [download_url][magnet_link] Start mirroring and upload the file/folder compressed with zip extension
unzipmirror - [download_url][magnet_link] Start mirroring and upload the file/folder extracted from any archive extension
zipleech - [download_url][magnet_link] Start leeching to Telegram and upload the file/folder compressed with zip extension
unzipleech - [download_url][magnet_link][torent_file] Start leeching to Telegram and upload the file/folder extracted from any archive extension
count - [drive_url][gdtot_url] Count file/folder of Google Drive
del - [drive_url] Delete file/folder from Google Drive (Only Owner & Sudo)
watch - [yt-dlp supported link] Mirror yt-dlp supported link 
zipwatch - [yt-dlp supported link] Mirror yt-dlp supported link as zip
leechwatch -  [yt-dlp supported link] Leech yt-dlp supported link
leechzipwatch - [yt-dlp supported link] Leech yt-dlp supported link as zip
dumpid - Add Dump Channel for leech files. make sure bot should an admin in dump channel.
leechset - Leech settings
setthumb - Reply photo to set it as Thumbnail
cancel - Reply to the message by which the download was initiated and that download will be cancelled
cancelall - /cancelall - Cancel all downloading tasks
list - [query] - Search in Google Drive(s)
search - [query] - Search for torrents with API
stats - Show Stats of the machine the bot is hosted on
ping - Check how long it takes to Ping the Bot
authorize - Authorize a chat or a user to use the bot (Can only be invoked by Owner & Sudo of the bot)
unauthorize - Unauthorize a chat or a user to use the bot (Can only be invoked by Owner & Sudo of the bot)
users - Show authorized users (Only Owner & Sudo)
addsudo - Add sudo user (Only Owner)
rmsudo - Remove sudo users (Only Owner)
paid - Show Paid users (Only Owner & Sudo)
addpaid - Authorize Paid users (Only Owner)
rmpaid - Unauthorize Paid users (Only Owner)
restart - Restart and update the bot (Only Owner & Sudo)
log - Get a log file of the bot. Handy for getting crash reports
```
------


## License ⚠️

[![](https://www.gnu.org/graphics/gplv3-with-text-136x68.png)](https://www.gnu.org/licenses/gpl-3.0.html)

```text
Copyright (C) 2022 WeebZone

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program. < https://github.com/weebzone/WZML/blob/update/LICENSE >.
```

---

## Contributors 🏆
<details>
    <summary><b>Click Here For Description</b></summary>

|![](https://avatars.githubusercontent.com/u/113664541)|![](https://avatars.githubusercontent.com/u/77075674)|![](https://avatars.githubusercontent.com/u/94453305)|![](https://avatars.githubusercontent.com/u/56303690)|![](https://avatars.githubusercontent.com/u/91935990)|![](https://avatars.githubusercontent.com/u/80155750)|
|---|---|---|---|---|---|
|[`CodeWithWeeb`](https://github.com/weebzone)|[`Anasty17`](https://github.com/anasty17)|[`Ajay Choudhary`](https://github.com/ajay0916) |[`Arshsisodiya`](https://github.com/arshsisodiya/helios-mirror) |[`ToxyTech`](https://github.com/dipeshpatil123)|[`MysterySD`](https://github.com/5MysterySD)|
| `me` add modules and fixes & many more|Base Repo|For suggestion & fixing| For there BOT_PM and LOG feature| For Task Limit| For Help and PIXIBAY Support|

</details>
