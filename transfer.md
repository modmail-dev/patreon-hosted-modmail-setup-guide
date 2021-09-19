## Transfer Existing Modmail Bot

[Go Back](/)

You have chosen to transfer over your existing Modmail bot to Patreon hosting. See below for your current hosting solution's transfer guide.
 - [Heroku](#heroku)
 - [Repl.it](#replit)
 - [Self Hosted (Other)](#self-hosted-other)


### Heroku

Navigate to [Heroku Dashboard](https://dashboard.heroku.com/apps){: target="_blank" rel="noopener"} on the heroku.com website, login if prompted. Choose the Modmail Bot application (does <u>not</u> have the *zzz* logo).

![Open Modmail Dashboard](https://i.imgur.com/GkOtJvR.png)

Click on the **Settings** tab. Scroll down to the **Config Vars** section and click on **Reveal Config Vars**.

![Reveal Config Vars](https://i.imgur.com/94n3KJX.png)

The page will display all your Modmail configs. Copy every field and send it back to Patreon Modmail DM.<br>**Note: it must include the token, MongoDB connection string, and guild ID.**

![Config Example](https://i.imgur.com/lXIaNzx.png)

If your bot is still running, navigate to the **Resources** tab, click on the pencil icon, turn off the worker switch, and press **confirm**. Otherwise, your bot may send duplicate messages.

![Turn off worker](https://i.imgur.com/GpwnwSB.gif)

Lastly, choose a memorable name for your Logviewer. You will be provided with a log URL under our **.modmail.dev** domain name. You can choose anything you like (with a few restrictions), if you feel it's reasonable, then most likely we do too! Note: only 3-16 alphanumeric characters are allowed. Send this to Patreon Modmail DM as well.


### Repl.it

Navigate to [My Repls](https://replit.com/repls){: target="_blank" rel="noopener"} on the repl.it website, login if prompted. Choose the Modmail Bot repl (not the logviewer's).

![Open Modmail Repl](https://i.imgur.com/q6kOBJJ.png)

On the side panel, click on the lock icon (Secret environment variables). Scroll down to the bottom and click **Open raw editor**.

![Find Repl Secret](https://i.imgur.com/zT6W00E.png){: style="max-width: 50%;"}

You will be greeted with a popup text box containing your secrets, copy everything in there and send back it to Patreon Modmail DM.<br>**Note: it must include the token, MongoDB connection string, and guild ID.**

![Secret Example](https://i.imgur.com/HvcvNd3.png)

If your bot is still running, press on the **Stop** button at the top and disable any uptime robots you may have enabled to stop the current bot from running. Otherwise, your bot may send duplicate messages.

Lastly, choose a memorable name for your Logviewer. You will be provided with a log URL under our **.modmail.dev** domain name. You can choose anything you like (with a few restrictions), if you feel it's reasonable, then most likely we do too! Note: only 3-16 alphanumeric characters are allowed. Send this to Patreon Modmail DM as well.


### Self Hosted (Other)

Whether you host with a Linux VPS, a Windows Server, a Raspberry PI, or even on your PC, the steps are similar. 

1. `cd` to the project's root folder or navigate to the project's root folder with the file browser on your machine.
2. Open the **.env** file (`cat .env` on Linux Terminal or `type .env` on Windows CMD).
3. Copy everything in there and send back it to Patreon Modmail DM.<br>**Note: it must include the token, MongoDB connection string, and guild ID.**
4. Stop the current bot from running.

Lastly, choose a memorable name for your Logviewer. You will be provided with a log URL under our **.modmail.dev** domain name. You can choose anything you like (with a few restrictions), if you feel it's reasonable, then most likely we do too! Note: only 3-16 alphanumeric characters are allowed. Send this to Patreon Modmail DM as well.


### What's Next?

After sending all the details back to the Patreon Modmail DM, we will validate everything you sent us. This process might take a few hours depends on our availability, so please bear with us while you wait. We will contact you when the bot is running or if there are any problems!

> This guide is written by taku#3343 with parts taken from the [Modmail Wiki](https://github.com/kyb3r/modmail/wiki/Installation).<br>
> If you have found any issues with this guide, please report them to me. Thanks ❤️!
