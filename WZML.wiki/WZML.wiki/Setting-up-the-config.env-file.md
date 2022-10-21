### NOTE
Remove the first line saying:
`_____REMOVE_THIS_LINE_____=True`

### REQUIRED VARIABLE
- `BOT_TOKEN`: The Telegram Bot Token that you got from [@BotFather](https://t.me/BotFather)
- `GDRIVE_FOLDER_ID`: This is the Folder/TeamDrive ID of the Google Drive Folder to which you want to upload all the mirrors.
- `OWNER_ID`: The Telegram User ID (not username) of the Owner of the bot. `Int`
- `DOWNLOAD_DIR`: The path to the local folder where the downloads should be downloaded to.
- `DOWNLOAD_STATUS_UPDATE_INTERVAL`: Time in seconds after which the progress/status message will be updated. Recommended `10` seconds at least. `Int`
- `AUTO_DELETE_MESSAGE_DURATION`: Interval of time (in seconds), after which the bot deletes it's message and command message which is expected to be viewed instantly. NOTE: Set to `-1` to disable auto message deletion. `Int`
- `AUTO_DELETE_UPLOAD_MESSAGE_DURATION`: Interval of time (in seconds), after which the bot deletes it's upload message and command message which is expected to be viewed instantly. NOTE: Set to `-1` to disable auto message deletion. `Int`
- `IS_TEAM_DRIVE`: Set True if uploading to TeamDrive. Default is `False`.
- `TELEGRAM_API`: This is to authenticate your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org/.
- `TELEGRAM_HASH`: This is to authenticate your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org/.

### OPTIONAL VARIABLE
- `DATABASE_URL`: Your SQL Database URL. Follow this [Generate Database](https://github.com/weebzone/WZML/wiki/Extra-Wiki#generate-database) to generate database. Data will be saved in Database: auth and sudo users, leech settings including thumbnails for each user, rss data and incomplete tasks. NOTE: If you want to use heroku postgresql delete this variable from config.env file. DATABASE_URL will be grabbed from heroku variables.
- `AUTHORIZED_CHATS`: Fill user_id and chat_id of groups/users you want to authorize. Separate them by space.
- `SUDO_USERS`: Fill user_id of users whom you want to give sudo permission. Separate them by space.
- `IGNORE_PENDING_REQUESTS`: Ignore pending requests after restart. Default is `False`.
- `USE_SERVICE_ACCOUNTS`: Whether to use Service Accounts or not. For this to work see [Using Service Accounts](https://github.com/weebzone/WZML/wiki/Deployment#using-service-accounts-for-uploading-to-avoid-user-rate-limit) section below. Default is `False`.
- `INDEX_URL`: Refer to https://gitlab.com/GoogleDriveIndex/Google-Drive-Index.
- `STATUS_LIMIT`: Limit the no. of tasks shown in status message with buttons. NOTE: Recommended limit is `3` tasks.
- `STOP_DUPLICATE`: Bot will check file in Drive, if it is present in Drive, downloading or cloning will be stopped. (NOTE: File will be checked using filename not file hash, so this feature is not perfect yet). Default is `False`.
- `CMD_INDEX`: commands index number. This number will added at the end all commands.
- `UPTOBOX_TOKEN`: Uptobox token to mirror uptobox links. Get it from [Uptobox Premium Account](https://uptobox.com/my_account).
- `TORRENT_TIMEOUT`: Timeout of dead torrents downloading with qBittorrent and Aria2c in seconds.
- `EXTENSION_FILTER`: File extensions that won't upload/clone. Separate them by space.
- `INCOMPLETE_TASK_NOTIFIER`: Get incomplete task messages after restart. Require database and (supergroup or channel). Default is `False`.

### TURN ON/OFF FUCTIONS VARIABLE
- `LEECH_ENABLED`: Enable or disable leech command for authorized chats. Default is `False`
- `MIRROR_ENABLED`: Enable or disable mirror command for authorized chats. Default is `False`
- `WATCH_ENABLED`: Enable or disable watch command for authorized chats. Default is `False`
- `CLONE_ENABLED`: Enable or disable clone command for authorized chats. Default is `False`
- `ANILIST_ENABLED`: Enable or disable anilist command for authorized chats. Default is `False`
- `WAYBACK_ENABLED`: Enable or disable wayback command for authorized chats. Default is `False`
- `MEDIAINFO_ENABLED`: Enable or disable mediainfo command for authorized chats. Default is `False`
- `SET_BOT_COMMANDS`: Auto set bot commands in bot i.e no need to set bot command manually using botfather. Default is `False`

### UPDATE VARIABLE
- `UPSTREAM_REPO`: Your github repository link, if your repo is private add `https://username:{githubtoken}@github.com/{username}/{reponame}` format. Get token from [Github settings](https://github.com/settings/tokens). So you can update your bot from filled repository on each restart. NOTE: Any change in docker or requirements you need to deploy/build again with updated repo to take effect. DON'T delete .gitignore file. For more information read [THIS](https://github.com/weebzone/WZML/wiki/Extra-Wiki#upstream-repo-recommended).
- `UPSTREAM_BRANCH`: Upstream branch for update. Default is `update`.

### LEECH MIRROR VARIABLE
- `BOT_PM`: set it `True` if you want to send mirror links and leeched files in user's PM, Default is `False`.
- `FORCE_BOT_PM`: set it `True` if you don't want to show the index link, drive link & other buttons (except source link and view file in pm button) in the group but all the buttons will show on the bot pm. `For this the BOT_PM must be True`. Default is `False`  
- `MIRROR_LOGS`: Chat id of channels/groups where you want to store Mirror logs, NOTE Add bot in Mirror logs channel/group as `Admin`.
- `MIRROR_LOG_URL`: Convert the join mirror log warning text on final upload message to your mirror log invite link. Add the `invite link` or either use the `public link` of mirror log channel.
- `LEECH_LOG`: Chat id of channel/group where leeched files will be uploaded, NOTE: only put `1 channel/group id` starts with `-100xxxxxxxxx`, NOTE add bot in that channel/group as `Admin`, if you leave this empty bot will sent leech files in current chat.
- `LEECH_LOG_URL`: Convert the join leech log warning text on final upload message to your leech log invite link. Add the `invite link` or either use the `public link` of leech log channel.
- `LEECH_LOG_INDEXING`: Set it to `True` if you also want Leech file indexing in Leech log channel. Default is `False`
- `LINK_LOG`: Chat id of channel/group where link have to be send, NOTE: only put `1 channel/group id` starts with `-100xxxxxxxxx`, NOTE add bot in that channel/group as `Admin`.
- `TG_SPLIT_SIZE`: Size of split in bytes. Default is `2GB`.
- `AS_DOCUMENT`: Default type of Telegram file upload. Default is `False` mean as `media`.
- `EQUAL_SPLITS`: Split files larger than TG_SPLIT_SIZE into equal parts size (Not working with zip cmd). Default is `False`.
- `CUSTOM_FILENAME`: Add custom word to leeched file name

### TELEGRAPH UI VARIABLE
- `TITLE_NAME`: Title name for Telegraph pages (while using /list command)
- `AUTHOR_NAME`: Author name for Telegraph pages
- `AUTHOR_URL`: Author URL for Telegraph page
- `GD_INFO`: Description of file uploaded to gdrive using bot

### FORCE SUB CHANNEL VARIABLE
- `FSUB`: Set it to `True` if you want to use the Force Subscriber Module. Default is `False`
- `CHANNEL_USERNAME`: Add the channel username without `@`
- `FSUB_CHANNEL_ID`: Add the channel id. eg `-100xxxxxx`

### QBITTORRENT VARIABLE
- `BASE_URL_OF_BOT`: Valid BASE URL where the bot is deployed to use qbittorrent web selection. Also required for Heroku to avoid app sleeping/idling. For Heroku fill `https://yourappname.herokuapp.com`. Still got idling? You can use http://cron-job.org/ to ping your Heroku app.
- `SERVER_PORT`: Not require for heroku.
- `WEB_PINCODE`: If empty or `False` means no more pincode required while qbit web selection.
- `QB_SEED`: QB torrent will be seeded after and while uploading until reaching specific ratio or time, edit `MaxRatio` or `GlobalMaxSeedingMinutes` or both from qbittorrent.conf (`-1` means no limit, but u can cancel manually by gid). NOTE: 1. Don't change `MaxRatioAction`, 2. Only works with `/qbmirror` and `/qbzipmirror`. Default is `False`. Bool
  - **Qbittorrent NOTE**: If your facing ram exceeded issue then set limit for `MaxConnecs`, decrease `AsyncIOThreadsCount` in qbittorrent config and set limit of `DiskWriteCacheSize` to `32`.

### RSS VARIABLE
- `RSS_DELAY`: Time in seconds for rss refresh interval. Recommended `900` second at least. Default is `900` in sec.
- `RSS_COMMAND`: Choose command (like /mirror, /qbmirror, /leech....) for the desired action.
- `RSS_CHAT_ID`: Chat ID where rss links will be sent. If using channel then add channel id.
- `USER_SESSION_STRING`: To send rss links from your telegram account instead of adding bot to channel then linking the channel to group to get rss link since bot will not read command from itself or other bot. To generate session string use this command `python3 generate_string_session.py` after mounting repo folder for sure.
  - **RSS NOTE**: `DATABASE_URL` and `RSS_CHAT_ID` is required, otherwise all rss commands will not work. You must use bot in group. You can add the bot to a channel and add link this channel to group so messages sent by bot to channel will be forwarded to group without using `USER_STRING_SESSION`.

### PRIVATE FILES VARIABLE
- `ACCOUNTS_ZIP_URL`: Only if you want to load your Service Account externally from an Index Link or by any direct download link NOT webpage link. Archive the accounts folder to ZIP file. Fill this with the direct download link of zip file. If index need authentication so add direct download as shown below:
  - `https://username:password@example.workers.dev/...`
- `TOKEN_PICKLE_URL`: Only if you want to load your **token.pickle** externally from an Index Link. Fill this with the direct link of that file.
- `MULTI_SEARCH_URL`: Check `drive_folder` setup [here](https://github.com/weebzone/WZML/wiki/Extra-Wiki#multi-search-ids). Write **drive_folder** file [here](https://gist.github.com/). Open the raw file of that gist, it's URL will be your required variable. Should be in this form after removing commit id: https://gist.githubusercontent.com/username/gist-id/raw/drive_folder
- `YT_COOKIES_URL`: Youtube authentication cookies. Check setup [Here](https://github.com/ytdl-org/youtube-dl#how-do-i-pass-cookies-to-youtube-dl). Use gist raw link and remove commit id from the link, so you can edit it from gists only.
- `NETRC_URL`: To create .netrc file contains authentication for aria2c and yt-dlp. Use gist raw link and remove commit id from the link, so you can edit it from gists only. **NOTE**: After editing .nterc you need to restart the docker or if deployed on heroku so restart dyno in case your edits related to aria2c authentication.
  - **NOTE**: All above url variables used incase you want edit them in future easily without deploying again or if you want to deploy from public fork. If deploying using cli or private fork you can leave these variables empty add token.pickle, accounts folder, drive_folder, .netrc and cookies.txt directly to root but you can't update them without rebuild OR simply leave all above variables and use private UPSTREAM_REPO.

### MEGA VARIABLE
- `MEGA_API_KEY`: Mega.nz API key to mirror mega.nz links. Get it from [Mega SDK Page](https://mega.nz/sdk)
- `MEGA_EMAIL_ID`: E-Mail ID used to sign up on mega.nz for using premium account.
- `MEGA_PASSWORD`: Password for mega.nz account.

### SHORTNER VARIABLE 
- `SHORTENER_API`: Fill your Shortener API key.
- `SHORTENER`: Shortener URL.
  - Supported URL Shorteners:
  >exe.io, gplinks.in, shrinkme.io, urlshortx.com, shortzon.com, bit.ly, shorte.st, linkvertise.com , ouo.io, adfoc.us, cutt.ly

### GDTOT COOKIE VARIABLE
- `CRYPT`: Cookie for gdtot google drive link generator. Follow these [steps](https://github.com/weebzone/WZML/wiki/Extra-Wiki#gdtot-cookies).

### UNIFIED LOGIN (AppDrive, DriveApp, GDFlix, DriveBit, DriveLinks, DriveSharer, DriveAce, DrivePro, Sharer)
- `UNIFIED_EMAIL` = Fill your Email address. (Note: Use same email in unified login sites.)
- `UNIFIED_PASS` = Password for login. (Same password for all sites.)

### HUBDRIVE COOKIES
- `HUBDRIVE_CRYPT` = Cookie for Hubdrive. Follow these [steps](https://github.com/weebzone/WZML/wiki/Extra-Wiki#gdtot-cookies).

### (KATDRIVE + KOLOP + DRIVEHUB) COOKIES
- `KATDRIVE_CRYPT` = Cookie for Katdrive, Kolop, Drivehub. Follow these [steps](https://github.com/weebzone/WZML/wiki/Extra-Wiki#gdtot-cookies).

### (DRIVEFIRE + DRIVEBUZZ) COOKIES
- `DRIVEFIRE_CRYPT` = Cookie for DriveFire, DriveBuzz. Follow these [steps](https://github.com/weebzone/WZML/wiki/Extra-Wiki#gdtot-cookies).

### Sharer.pw COOKIES
- `XSRF_TOKEN` = For XSRF Token use this chrome extension: [Cick here to download](https://chrome.google.com/webstore/detail/get-cookiestxt/bgaddhkoddajcdgocldbbfleckgcbcid)
- `laravel_session` = For Laravel session use the same extension addressed above: [Click here to download](https://chrome.google.com/webstore/detail/get-cookiestxt/bgaddhkoddajcdgocldbbfleckgcbcid)

### SIZE LIMIT VARIABLE
- `TORRENT_DIRECT_LIMIT`: To limit the Torrent/Direct mirror size. Don't add unit. Default unit is `GB`.
- `ZIP_UNZIP_LIMIT`: To limit the size of zip and unzip commands. Don't add unit. Default unit is `GB`.
- `CLONE_LIMIT`: To limit the size of Google Drive folder/file which you can clone. Don't add unit. Default unit is `GB`.
- `MEGA_LIMIT`: To limit the size of Mega download. Don't add unit. Default unit is `GB`.
- `STORAGE_THRESHOLD`: To leave specific storage free and any download will lead to leave free storage less than this value will be cancelled. Don't add unit. Default unit is `GB`
- `ACTIVE_TASK_LIMIT`: To limit the Total task for the bot, `unrestricted for owner and sudo`. use the `integer`
- `USER_TASKS_LIMIT`: Limit the task for every users of group, `unrestricted for owner and sudo`. use the `integer`
- `LEECH_LIMIT`: To limit the Leeching. Don't add unit. Default unit is `GB`.

### PROGRESS STRINGS VARIABLE
- `FINISHED_PROGRESS_STR`: Change finish progress bar icon, Default is `●`
- `UN_FINISHED_PROGRESS_STR`: Change unfinish progress bar icon, Default is `○`

### THEME VARIABLE
- `EMOJI_THEME`: Change Theme from simple look to emoji version, Default is `False`
- `SHOW_LIMITS_IN_STATS`: Make it to `True` if you want to show the bot limits in Stats message. Default is `False`

### VIEW STYLE
- `TELEGRAPH_STYLE`: Set it to `True` if you want Telegrah Format for list, search etc, instead of HTML format. Default is `False`

### BRANDING
- `CREDIT_NAME`: Replace the Branding of repo with Your Custom name

### DYNAMIC IMAGES
- `PICS`: Add multiple telgraph image links that are seperated by spaces. It set the images for Start, stats, and for all mirror and leech commands.

### FONT STYLE
- `NAME_FONT`: Change the Filename style on Upload message, Available Options : `b`, `code`, `i`, `u`, `strike`, `spoiler`. Default is `code`
- `CAPTION_FONT`: Change the Caption of Leeched files, Available Options : `b`, `code`, `i`, `u`, `strike`, `spoiler`. Default is `code`

### Buttons
- `DISABLE_DRIVE_LINK`: Directly disable for drive link button. Default is `False`
- `VIEW_LINK`: View Link button to open file Index Link in browser instead of direct download link, you can figure out if it's compatible with your Index code or not, open any video from you Index and check if its URL ends with `?a=view`, if yes make it `True`, compatible with [BhadooIndex](https://gitlab.com/GoogleDriveIndex/Google-Drive-Index) Code. Default is `False`.
- `SOURCE_LINK`: View the Source Link button of The mirror or leech file/link. Default is `False`
- `START_BTN1_NAME`: Change start button one name
- `START_BTN1_URL`: add Url of start button one
- `START_BTN2_NAME`: Change start button two name
- `START_BTN2_URL`: add Url of start button two
- Three buttons are already added including Drive Link, Index Link, and View Link, you can add extra buttons, if you don't know what are the below entries, simply leave them empty.
  - `BUTTON_FOUR_NAME`:
  - `BUTTON_FOUR_URL`:
  - `BUTTON_FIVE_NAME`:
  - `BUTTON_FIVE_URL`:
  - `BUTTON_SIX_NAME`:
  - `BUTTON_SIX_URL`:

### Torrent Search
- `SEARCH_API_LINK`: Search api app link. Get your api from deploying this [repository](https://github.com/Ryuk-me/Torrent-Api-py).
  - Supported Sites:
  >1337x, Piratebay, Nyaasi, Torlock, Torrent Galaxy, Zooqle, Kickass, Bitsearch, MagnetDL, Libgen, YTS, Limetorrent, TorrentFunk, Glodls, TorrentProject and YourBittorrent
- `SEARCH_LIMIT`: Search limit for search api, limit for each site and not overall result limit. Default is zero (Default api limit for each site).
- `SEARCH_PLUGINS`: List of qBittorrent search plugins (github raw links). I have added some plugins, you can remove/add plugins as you want. Main Source: [qBittorrent Search Plugins (Official/Unofficial)](https://github.com/qbittorrent/search-plugins/wiki/Unofficial-search-plugins).