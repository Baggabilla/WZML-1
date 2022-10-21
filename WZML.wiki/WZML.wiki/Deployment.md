## Getting Google OAuth API credential file and token.pickle

**NOTES**
- Old authentication changed, now we can't use bot or replit to generate token.pickle. You need OS with a browser.
- Windows users should install python3 and pip.
- You can ONLY open the generated link from `generate_drive_token.py` in local browser.

1. Visit the [Google Cloud Console](https://console.developers.google.com/apis/credentials)
2. Go to the OAuth Consent tab, fill it, and save.
3. Go to the Credentials tab and click Create Credentials -> OAuth Client ID
4. Choose Desktop and Create.
5. Publish your OAuth consent screen App to prevent **token.pickle** from expire
6. Use the download button to download your credentials.
7. Move that file to the root of mirrorbot, and rename it to **credentials.json**
8. Visit [Google API page](https://console.developers.google.com/apis/library)
9. Search for Google Drive Api and enable it
10. Finally, run the script to generate **token.pickle** file for Google Drive:
```
pip3 install google-api-python-client google-auth-httplib2 google-auth-oauthlib
python3 generate_drive_token.py
```

## Using Service Accounts for uploading to avoid user rate limit
>For Service Account to work, you must set `USE_SERVICE_ACCOUNTS` = "True" in config file or environment variables.
>**NOTE**: Using Service Accounts is only recommended while uploading to a Team Drive.

### 1. Generate Service Accounts. [What is Service Account?](https://cloud.google.com/iam/docs/service-accounts)
Let us create only the Service Accounts that we need.

**Warning**: Abuse of this feature is not the aim of this project and we do **NOT** recommend that you make a lot of projects, just one project and 100 SAs allow you plenty of use, its also possible that over abuse might get your projects banned by Google.

>**NOTE**: If you have created SAs in past from this script, you can also just re download the keys by running:
```
python3 gen_sa_accounts.py --download-keys $PROJECTID
```
>**NOTE:** 1 Service Account can upload/copy around 750 GB a day, 1 project can make 100 Service Accounts so you can upload 75 TB a day or clone 2 TB from each file creator (uploader email).

#### Two methods to create service accounts
Choose one of these methods

##### 1. Create Service Accounts in existed Project (Recommended Method)
- List your projects ids
```
python3 gen_sa_accounts.py --list-projects
```
- Enable services automatically by this command
```
python3 gen_sa_accounts.py --enable-services $PROJECTID
```
- Create Sevice Accounts to current project
```
python3 gen_sa_accounts.py --create-sas $PROJECTID
```
- Download Sevice Accounts as accounts folder
```
python3 gen_sa_accounts.py --download-keys $PROJECTID
```

##### 2. Create Service Accounts in New Project
```
python3 gen_sa_accounts.py --quick-setup 1 --new-only
```
A folder named accounts will be created which will contain keys for the Service Accounts.

### 2. Add Service Accounts

#### Two methods to add service accounts
Choose one of these methods

##### 1. Add Them To Google Group then to Team Drive (Recommended)
- Mount accounts folder
```
cd accounts
```
- Grab emails form all accounts to emails.txt file that would be created in accounts folder
- `For Windows using PowerShell`
```
$emails = Get-ChildItem .\**.json |Get-Content -Raw |ConvertFrom-Json |Select -ExpandProperty client_email >>emails.txt
```
- `For Linux`
```
grep -oPh '"client_email": "\K[^"]+' *.json > emails.txt
```
- Unmount acounts folder
```
cd ..
```
Then add emails from emails.txt to Google Group, after that add this Google Group to your Shared Drive and promote it to manager and delete email.txt file from accounts folder

##### 2. Add Them To Team Drive Directly
- Run:
```
python3 add_to_team_drive.py -d SharedTeamDriveSrcID
```
------

# Deploying on VPS

**IMPORTANT NOTES**:
1. You must set `SERVER_PORT` variable to `80` or any other port you want to use.
2. To clear the container (this will not affect on the image):
```
sudo docker container prune
```
3. To delete the images:
```
sudo docker image prune -a
```
4. Check the number of processing units of your machine with `nproc` cmd and times it by 4, then edit `AsyncIOThreadsCount` in qBittorrent.conf.
5. You can add `CONFIG_FILE_URL` variable using docker and docker-compose, google it.

------

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
- To stop the image:
```
sudo docker ps
```
```
sudo docker stop id
```

----

## Deploying on VPS Using docker-compose

**NOTE**: If you want to use port other than 80, change it in [docker-compose.yml](https://github.com/anasty17/weebzone/WZML/blob/master/docker-compose.yml) also.

```
sudo apt install docker-compose
```
- Build and run Docker image:
```
sudo docker-compose up
```
- After editing files with nano for example (nano start.sh):
```
sudo docker-compose up --build
```
- To stop the image:
```
sudo docker-compose stop
```
- To run the image:
```
sudo docker-compose start
```

------

# Heroku Deploy

**Important Notes**
1. Generate all your private files from master branch (token.pickle, config.env, drive_folder, cookies.txt, accounts, .netrc) since the generators not available in heroku branch but you should add the private files in heroku branch not in master or use variables links in `config.env`. (recommended use the private files index links in the `config.env`)
2. Don't add variables in heroku Environment, you can only add `CONFIG_FILE_URL`.
3. Don't deploy using hmanager or github integration.
4. To avoid idling fill `BASE_URL_OF_BOT` or you can use [corn-job](http://cron-job.org) to ping your Heroku app.
5. If you want to edit anything in code, so u should edit [update branch](https://github.com/codewithweeb/mirror-with-weeb/tree/update). After that u should add fill `UPSTREAM_REPO` of your fork and leave `UPSTREAM_BRANCH` empty since it's by default `update`.
6. This branch use megasdkrest and latest version of qBittorrent....


------

## Deploy With CLI

- Clone this repo:
```
git clone https://github.com/weebzone/WZML mirrorbot/ && cd mirrorbot
```
- Switch to heroku branch
  - **NOTE**: Don't commit changes in master branch. If you have committed your changes in master branch and after that you switched to heroku branch, the new added files(private files) will `NOT` appear in heroku branch.
```
git checkout heroku
```
- After adding your private files
```
git add . -f
```
- Commit your changes
```
git commit -m token
```
- Login to heroku
```
heroku login
```
- Create heroku app
```
heroku create --region us YOURAPPNAME
```
- Add remote
```
heroku git:remote -a YOURAPPNAME
```
- Create container
```
heroku stack:set container
```
- Push to heroku
```
git push heroku heroku:master -f
```

------

### Extras

- To create heroku-postgresql database
```
heroku addons:create heroku-postgresql
```
- To delete the app
```
heroku apps:destroy YOURAPPNAME
```
- To restart dyno
```
heroku restart
```
- To turn off dyno
```
heroku ps:scale web=0
```
- To turn on dyno
```
heroku ps:scale web=1
```
- To set heroku variable
```
heroku config:set VARNAME=VARTEXT
```
- To get live logs
```
heroku logs -t
```

------

## Deploy With Github Workflow

1. Go to Repository Settings -> Secrets

![Secrets](https://telegra.ph/file/9d6ed26f8981c2d2f226c.jpg)

2. Add the below Required Variables one by one by clicking New Repository Secret every time.

   - HEROKU_EMAIL: Heroku Account Email Id in which the above app will be deployed
   - HEROKU_API_KEY: Your Heroku API key, get it from https://dashboard.heroku.com/account
   - HEROKU_APP_NAME: Your Heroku app name, Name Must be unique
   - CONFIG_FILE_URL: Copy [This](https://raw.githubusercontent.com/weebzone/WZML/heroku/config_sample.env) in any text editor. Remove the _____REMOVE_THIS_LINE_____=True line and fill the variables. For details about config you can see Here. Go to https://gist.github.com and paste your config data. Rename the file to config.env then create secret gist. Click on Raw, copy the link. This will be your CONFIG_FILE_URL. Refer to below images for clarity.

![Steps from 1 to 3](https://telegra.ph/file/eb030f86f4e04cbfe624b.png)

![Step 4](https://telegra.ph/file/dae906ea139ecbf9e82ff.png)

![Step 5](https://telegra.ph/file/ea4d55d12d2d7fb45e24b.png)

3. Remove commit id from raw link to be able to change variables without updating the CONFIG_FILE_URL in secrets. Should be in this form: https://gist.githubusercontent.com/username/gist-id/raw/config.env
   - Before: https://gist.githubusercontent.com/codewithweeb/8cce4a4b4e7f4ea47e948b2d058e52ac/raw/19ba5ab5eb43016422193319f28bc3c7dfb60f25/config.env
   - After: https://gist.githubusercontent.com/codewithweeb/8cce4a4b4e7f4ea47e948b2d058e52ac/raw/config.env

4. Add all your private files in this branch or use variables links in `config.env`.

5. After adding all the above Required Variables go to Github Actions tab in your repository.
   - Select Manually Deploy to Heroku workflow as shown below:

![Select Manual Deploy](https://telegra.ph/file/fb1a396acef1aa97b7853.png)

6. Choose `heroku` branch and click on Run workflow

![Run Workflow](https://telegra.ph/file/6dafe409e04b93f9606fc.png)

------
