## Bot commands to be set in [@BotFather](https://t.me/BotFather)

```
mirror - Mirror
zipmirror - Mirror and upload as zip
unzipmirror - Mirror and extract files
qbmirror - Mirror torrent using qBittorrent
qbzipmirror - Mirror torrent and upload as zip using qb
qbunzipmirror - Mirror torrent and extract files using qb
leech - Leech
zipleech - Leech and upload as zip
unzipleech - Leech and extract files
qbleech - Leech torrent using qBittorrent
qbzipleech - Leech torrent and upload as zip using qb
qbunzipleech - Leech torrent and extract using qb
clone - Copy file/folder to Drive
count - Count file/folder of Drive
watch - Mirror yt-dlp supported link
zipwatch - Mirror yt-dlp supported link as zip
leechwatch - Leech through yt-dlp supported link
leechzipwatch - Leech yt-dlp support link as zip
leechset - Leech settings
setthumb - Set thumbnail
status - Get Mirror Status message
rsslist - List all subscribed rss feed info
rssget - Get specific No. of links from specific rss feed
rsssub - Subscribe new rss feed
rssunsub - Unsubscribe rss feed by title
rssset - Rss Settings
list - Search files in Drive
search - Search for torrents with API
cancel - Cancel a task
cancelall - Cancel all tasks
del - Delete file/folder from Drive
log - Get the Bot Log
speedtest - Get server speedtest
mediainfo - Get information of media files
hash - Get Hash of telegram files
wayback - Internet archive 
shell - Run commands in Shell
restart - Restart the Bot
stats - Bot Usage Stats
usage - Heroku app usage
ping - Ping the Bot
help - All cmds with description

```
------

## UPSTREAM REPO (Recommended)

- `UPSTREAM_REPO` variable can be used for edit/add any file in repository.
- You can add private/public repository link to grab/overwrite all files from it.
- You can skip adding the privates files like token.pickle or accounts folder before deploying, also no need to add variables direct links except **config.env**, simply fill `UPSTREAM_REPO` private one in case you want to grab all files including private files.
- If you added private files while deploying and you have added private `UPSTREAM_REPO` and your private files in this private repository, so your private files will be overwritten from this repository. Also if you are using URL variables like `TOKEN_PICKLE_URL` then all files from those variables will override the private files that added before deploying or from private `UPSTREAM_REPO`.
- If you filled `UPSTREAM_REPO` with the official repository link then be carefull incase any change in requirements.txt your bot will not start after restart. In this case you need to deploy again with updated code to install the new requirements or simply by changing the `UPSTREAM_REPO` to you fork link with that old updates or make it empty if deployed master branch.
- In case you you filled `UPSTREAM_REPO` with your fork link be carefull also if you fetched the commits from the official repository.
- The changes in your `UPSTREAM_REPO` will take affect only after restart.
- `UPSTREAM_BRANCH` don't ever fill heroku here.

------

## Generate Database

**1. Using Railway**
- Go to [railway](https://railway.app) and create account
- Start new project
- Press on `Provision PostgreSQL`
- After creating database press on `PostgresSQL`
- Go to `Connect` column
- Copy `Postgres Connection URL` and fill `DATABASE_URL` variable with it

**2. Using Heroku PostgreSQL**
<p><a href="https://dev.to/prisma/how-to-setup-a-free-postgresql-database-on-heroku-1dc1"> <img src="https://img.shields.io/badge/See%20Dev.to-black?style=for-the-badge&logo=dev.to" width="160""/></a></p>

**3. Using ElephantSQL**
- Go to [elephantsql](https://elephantsql.com) and create account
- Hit `Create New Instance`
- Follow the further instructions in the screen
- Hit `Select Region`
- Hit `Review`
- Hit `Create instance`
- Select your database name
- Copy your database url, and fill `DATABASE_URL` variable with it

------

## Multi Search IDs
To use list from multi TD/folder. Run driveid.py in your terminal and follow it. It will generate **drive_folder** file or u can simply create `drive_folder` file in working directory and fill it, check below format:
```
MyTdName folderID/tdID IndexLink(if available)
MyTdName2 folderID/tdID IndexLink(if available)
```
-----

## Yt-dlp and Aria2c Authentication Using .netrc File
For using your premium accounts in yt-dlp or for protected Index Links, create .netrc file according to following format:

**Note**: Create .netrc and not netrc, this file will be hidden, so view hidden files to edit it after creation.

Format:
```
machine host login username password my_password
```
Example:
```
machine instagram login anas.tayyar password mypassword
```
**Instagram Note**: You must login even if you want to download public posts and after first try you must confirm that this was you logged in from different ip(you can confirm from phone app).

**Youtube Note**: For `youtube` authentication use [cookies.txt](https://github.com/ytdl-org/youtube-dl#how-do-i-pass-cookies-to-youtube-dl) file.

Using Aria2c you can also use built in feature from bot with or without username. Here example for index link without username.
```
machine example.workers.dev password index_password
```
Where host is the name of extractor (eg. instagram, Twitch). Multiple accounts of different hosts can be added each separated by a new line.

-----

## Gdtot Cookies
To Clone or Leech gdtot link follow these steps:
1. Login/Register to [gdtot](https://new.gdtot.top).
2. Copy this script and paste it in browser address bar.
   - **Note**: After pasting it check at the beginning of the script in broswer address bar if `javascript:` exists or not, if not so write it as shown below.
   ```javascript
   javascript:(function () {
    const input = document.createElement('input');
    COOKIE = JSON.parse(JSON.stringify({cookie : document.cookie}));
    input.value = COOKIE['cookie'].split('crypt=')[1];
    document.body.appendChild(input);
    input.focus();
    input.select();
    var result = document.execCommand('copy');
    document.body.removeChild(input);
     if(result)
       alert('Crypt copied to clipboard');
     else
       prompt('Failed to copy Crypt. Manually copy below Crypt\n\n', input.value);
   })();
   ```
   - After pressing enter your browser will prompt a alert.
3. Now you'll get Crypt value in your clipboard
   ```
   NGxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxWdSVT0%3D
   ```
4. From this you have to paste value for **CRYPT** in config.env file.


## Unified Cookies
To Clone or Leech AppDrive, DriveApp, GDFlix, DriveBit, DriveLinks, DriveSharer, DriveAce, DrivePro link follow these steps:
1. Login/Register to [AppDrive](https://appdrive.in/).
   Login/Register to [DriveApp](https://driveapp.in/).
   Login/Register to [GDFlix](https://gdflix.pro/).
   Login/Register to [DriveBit](https://drivebit.in/).
   Login/Register to [DriveLinks](https://drivelinks.in/).
   Login/Register to [DriveSharer](https://drivesharer.in/).
   Login/Register to [DriveAce](https://driveace.in/).
   Login/Register to [DrivePro](https://drivepro.in/).

2. Copy this script and paste it in browser address bar.
   - **Note**: After pasting it check at the beginning of the script in broswer address bar if `javascript:` exists or not, if not so write it as shown below.
   ```javascript
   javascript:(function () {
    const input = document.createElement('input');
    COOKIE = JSON.parse(JSON.stringify({cookie : document.cookie}));
    input.value = COOKIE['cookie'].split('crypt=')[1];
    document.body.appendChild(input);
    input.focus();
    input.select();
    var result = document.execCommand('copy');
    document.body.removeChild(input);
     if(result)
       alert('Crypt copied to clipboard');
     else
       prompt('Failed to copy Crypt. Manually copy below Crypt\n\n', input.value);
   })();
   ```
   - After pressing enter your browser will prompt a alert.
3. Now you'll get Crypt value in your clipboard
   ```
   NGxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxWdSVT0%3D
   ```
4. From this you have to paste value for **CRYPT** in config.env file.

-----