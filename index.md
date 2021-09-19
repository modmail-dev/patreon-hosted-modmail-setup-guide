## Thank you for subscribing to Patreon!

Welcome to Patreon hosting! Before we can start hosting your new Modmail bot, we will need some bot infos from you—namely a Discord bot token, an external MongoDB database, and some other minor things. This way, you will be the full owner of your Discord bot and have control over the stored data. By the end of this guide, we will hopefully have generated everything we need for bot hosting.

If you already hosting an existing Modmail bot and would rather transfer that over, **click here** to find out how!

### Getting Started

#### What you'll need:
 - An internet connection and browser.
 - An email account.
 - ~15 minutes of your time.

**It's crucial to follow every step carefully! Missing any step might increase the final setup time.**


### Step 1 - Creating Discord Bot Account

You will need to create a bot application to interact with the Discord API. Head over to the [Applications Page](https://discordapp.com/developers/applications/). Log in - if you're not already - and click on **New Application**. Give it any name and click **Confirm** to register your bot. 

![Discord New Application](https://i.imgur.com/sTsk6wz.png)

Here you can customize your bot with a profile picture and an "About Me" section. Afterwards, press on the **Bot** tab, click on **Add Bot**, then choose **Yes, do it!** to confirm.

![Discord Build-A-Bot](https://i.imgur.com/6MikkYq.png)

If you choose to customize your bot, be sure to update the profile picture here too and choose a username for your bot. Once that's complete, scroll down and <u>disable</u> **Public Bot** and <u>enable</u> **Server Members Intent**. Don't forget to press the green **Save Changes** button!

![Discord Bot Settings](https://i.imgur.com/WljgVfP.png)

Next we need to grab the bot's token (aka. your bot's login credentials). Simply, scroll back to the top of that page, and click copy.

**Make sure to keep the token private. Anyone who has it can control (or "hack") your bot and will cause malicious damage to your server. If you feel that your token has been leaked, click on `Regenerate` to invalidate the old one and create a new bot token (you'll need to update us with your new token after regenerating it).**

![Discord Token](https://i.imgur.com/1G8oQ8V.png)

Example token format (shortened): `abcdefg.abcde.abcdefg12345`

Paste your token that you copied here (this website is static—nothing is stored and no data is sent to any servers. Unless your browser is hacked, you're perfectly safe to paste your token here):

**Token:** <input id="token" pattern="[a-zA-Z0-9-_]+\.[a-zA-Z0-9-_]+\.[a-zA-Z0-9-_]+" onchange="document.getElementById('enteredtoken').innerText = 'TOKEN=' + this.value; document.getElementById('invitelink').href = document.getElementById('invitelink').innerText = 'https://discord.com/oauth2/authorize?scope=bot&permissions=2953309432&client_id=' + atob(this.value.split('.')[0])">


### Step 2 - Inviting Your Discord Bot

Click on the following invite link to invite your bot and follow the Discord prompt. All permissions excepted for **Administrator** is <u>required</u>! But we recommend allowing **Administrator** for ease of setup and avoid permission complications.

**Invite link:** <a id="invitelink">Invalid</a>
(If you don't see an invite link or it appears as invalid, it means you didn't input your token on the previous step or your browser is out of date. **Click here** to manually make an invite link.)


### Step 3 - Creating a MongoDB Database

Modmail supports MongoDB and you are required to provide a MongoDB connection string for your bot. [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) provides a free 500MB tier, which is more than enough to store around 3 million message logs.

![GIF on Creating MongoDB](https://i.imgur.com/A7S2nPJ.gif)

#### Sign Up

Complete the sign up form and verify your email. Afterwards, choose "Shared" (free) database when asked. 

![Choosing Shard Database](https://i.imgur.com/lGchKpq.png)

On the following page, choose any of the **North America** region. Make sure the Cluster Type is set to **M0 Sandbox** and **MongoDB 4.4** or newer. Cluster name is irrelevant. 

### Create Database User

Click on **Database Access** on the sidebar, then click the green **Add New Database User** button in the middle. Set the username to `modmail` and password to something random (only letters and numbers, **no symbols**!). <u>You will need to share us this password so don't make it personal</u>. Privileges needs to be set as **Read and write to any database** or **Atlas admin**. Then click the **Add User** button at the bottom.

![Create Database User](https://i.imgur.com/TI1R4nN.png)

<div id="enteredtoken"></div>

