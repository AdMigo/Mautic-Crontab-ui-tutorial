
# Mautic-Crontab-ui-tutorial

I like to use Crontab-ui by @alseambusher to manage my Mautic Instace Commands as it handles the Crontab Graphically, takes backups, can send you monitoring emails over your Cron Job statuses (Don't you just hate having to manually check the Logs?🤬) - and more!

You can find Crontab-ui here: https://github.com/alseambusher/crontab-ui

Anyway here is a quick rundown of how to install Crontab-ui on a Ubuntu 18.04 Digital Ocean Server - You should have Mautic Installed on the same server which you install Crontab (It does not matter if the Chicken or Egg comes first🐣) 

Install NodeJS and NPM with the following Commands:

```sudo apt-get install curl -y```

```curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -```

```sudo apt-get install nodejs -y```

---------------------------------
Check NodeJS & NPM Version numbers with the following commands:

```node -v```

```npm -v```

---------------------------------
Install NodeJS Addons & Yarn Package Manager:

```sudo apt-get install gcc g++ make -y```

```curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -```

```echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list```

```sudo apt-get update && sudo apt-get install yarn -y```

--------------------------------
Install Crontab-UI with the following Commands:
```sudo npm install -g crontab-ui -y```

```sudo crontab-ui```       (This will be an initial Crontab-UI dry run)

Use the CTRL-C Command to shut down Crontab-ui after the initial dry run
-------------------------------
Use the following commands to launch Crontab UI for remote host with basic HTTP Auth:

```sudo HOST=0.0.0.0 PORT=8000 BASIC_AUTH_USER=user BASIC_AUTH_PWD=SecretPassword crontab-ui --autosave```

You can remove the ```--autosave``` flag if you do not wish to save Crons created within Crontab-ui to your Mautic Crontab

-------------------------------
From this point you will then be able to open crontab ui in your browser with a basic http auth login

Navigate directly to your Server IP Address & Port 8000 to access the crontab ui instance, simply input your username and password to add the cron jobs. 

When adding cronjobs be sure to click the 'SAVE TO CRONTAB" Button after making any changes to cron's be it adding, deleting, or editing exisiting crons
-------------------------------
Use CTRL-C to close the Crontab-ui instance anytime you are finshed with the cron work.
-------------------------------
Notes:

If you have any access error when installing Crontab use this tutoirial over chnaging your permissions, although if you install as sudo (root) then you should not encounter this issue.

https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally

You May uninstall Crontab-ui anytime with the following Command:

```sudo npm uninstall -g crontab-ui -y```

You May Reset Crontab-ui with the following command:

```crontab-ui --reset```

Crontab-ui is located within the following Apache Directory:

```/usr/lib/node_modules/crontab-ui/crontabs/```

If you do not shut down the Crontab-ui via Ctrl-C, then simply shut down the Server, if you are using a Digital Ocean Server you can run

```poweroff```


-------------------------------------------
