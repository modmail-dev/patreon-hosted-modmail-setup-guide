## Thank you for subscribing to Patreon!

Welcome to Patreon hosting! Before we can start hosting your new Modmail bot, we will need some bot infos from you—namely a Discord bot token, an external MongoDB database, and some other minor things. This way, you will be the full owner of your Discord bot and have control over the stored data. By the end of this guide, we will hopefully have generated everything we need for bot hosting.

If you already hosting an existing Modmail bot and would rather transfer that over, **click here** to find out how!

### Getting Started

#### What you'll need:
 - An internet connection and browser.
 - An email account.
 - ~15 minutes of your time.

There will be a few input boxes throughout this page, these are only for your convenience, this website is fully static hosted—meaning nothing is stored and no data is sent to any servers. Unless your browser is hacked, you're perfectly safe to paste anything here. <u>Keep a copy of everything you paste elsewhere—in case your browser crashes or reloads.</u>

**It's crucial to follow every step carefully! Missing any step might increase the final setup time.**


### Step 1 - Creating Discord Bot Account

You will need to create a bot application to interact with the Discord API. Head over to the [Applications Page](https://discordapp.com/developers/applications/"){: target="_blank" rel="noopener"}. Log in - if you're not already - and click on **New Application**. Give it any name and click **Confirm** to register your bot. 

![Discord New Application](https://i.imgur.com/sTsk6wz.png)

Here you can customize your bot with a profile picture and an "About Me" section. Afterwards, press on the **Bot** tab, click on **Add Bot**, then choose **Yes, do it!** to confirm.

![Discord Build-A-Bot](https://i.imgur.com/6MikkYq.png)

If you choose to customize your bot, be sure to update the profile picture here too and choose a username for your bot. Once that's complete, scroll down and <u>disable</u> **Public Bot** and <u>enable</u> **Server Members Intent**. Don't forget to press the green **Save Changes** button!

![Discord Bot Settings](https://i.imgur.com/WljgVfP.png)

Next we need to grab the bot's token (aka. your bot's login credentials). Simply, scroll back to the top of that page, and click copy.

**Make sure to keep the token private. Anyone who has it can control (or "hack") your bot and will cause malicious damage to your server. If you feel that your token has been leaked, click on `Regenerate` to invalidate the old one and create a new bot token (you'll need to update us with your new token after regenerating it).**

![Discord Token](https://i.imgur.com/1G8oQ8V.png)

Example token format (shortened): `abcdefg.abcde.abcdefg12345`

Paste your token that you copied here:

**Token:** <input id="token" oninput="document.getElementById('enteredtoken').innerText = 'TOKEN=' + this.value; document.getElementById('invitelink').href = document.getElementById('invitelink').innerText = 'https://discord.com/oauth2/authorize?scope=bot&permissions=2953309432&client_id=' + atob(this.value.split('.')[0]);">


### Step 2 - Inviting Your Discord Bot

Click on the following invite link to invite your bot and follow the Discord prompt. All permissions excepted for **Administrator** is <u>required</u>! But we recommend allowing **Administrator** for ease of setup and avoid permission complications.

**Invite link:** <a target="_blank" rel="noopener" id="invitelink">Invalid</a>
(If you don't see an invite link or it appears as invalid, it means you didn't input your token on the previous step or your browser is out of date. **Click here** to manually make an invite link.)

After the bot's invited to your server, you will see the bot offline in the members list—that is perfectly normal! It will come online when we start hosting.


### Step 3 - Find Your Guild (Server) ID

Please enter the ID of your guild. If you're unsure where to find the guild ID, Discord provides a short guide to help you: [https://dis.gd/FindMyID](https://dis.gd/FindMyID){: target="_blank" rel="noopener"}!

**Guild ID:** <input id="guild" oninput="document.getElementById('enteredguild').innerText = 'GUILD_ID=' + this.value;">

**Optional**, if you operate a large community and has a separate guild for staff activity, Modmail supports that too! Make sure Modmail is invited to <u>both</u> guilds with **Step 2**. You can supply your staff guild ID here:

**Staff Guild ID (optional):** <input id="staffguild" oninput="document.getElementById('enteredstaffguild').innerText = 'MODMAIL_GUILD_ID=' + this.value;">


### Step 4 - Creating a MongoDB Database

Modmail supports MongoDB and you are required to provide a MongoDB connection string for your bot. [MongoDB Atlas](https://www.mongodb.com/cloud/atlas){: target="_blank" rel="noopener"} provides a free 500MB tier, which is more than enough to store around 3 million message logs.

![GIF on Creating MongoDB](https://i.imgur.com/A7S2nPJ.gif)

### Sign Up

Complete the sign up form and verify your email. Afterwards, choose "Shared" (free) database when asked. 

![Choosing Shard Database](https://i.imgur.com/lGchKpq.png)

On the following page, choose any of the **North America** region. Make sure the Cluster Type is set to **M0 Sandbox** and **MongoDB 4.4** or newer. Cluster name is irrelevant. 

### Create Database User

Click on **Database Access** on the sidebar, then click the green **Add New Database User** button in the middle. Set the username to `modmail` and password to something random (only letters and numbers, **no symbols**!). <u>You will need to share us this password so don't make it personal</u>. Privileges needs to be set as **Read and write to any database** or **Atlas admin**. Then click the **Add User** button at the bottom.

![Create Database User](https://i.imgur.com/TI1R4nN.png)

### Whitelist All IP

Click on **Network Access** on the sidebar, then click the green **Add IP Address** button in the middle. Click on **ALLOW ACCESS FROM EVERYWHERE**, make sure `0.0.0.0/0` shows up below. Press **Confirm** to save the changes.

![Whitelist IP Address](https://i.imgur.com/53nWYjK.png)

### Retrieve the Database Connection String (URI)

Click on **Databases** on the sidebar, press **Connect**. If the button is grayed out, that means the database is still being created. It may take up to 15 minutes for the database to deploy; refresh/reload the webpage once in a while. After pressing **Connect**, choose the second option **Connect your application**. On the following screen, the driver doesn't matter, copy the entire provided connection string.

**You must substitute the `<password>` within the connection string with the password you set when creating the database user!**

![Database URI](https://i.imgur.com/tqiGwag.png)

Example connection string format: `mongodb+srv://modmail:somepassword@cluster0.abcde.mongodb.net`

Paste your connection string that you copied here (remember to replace `<password>` with the database user password!):

**Connection String:** <input id="mongo" oninput="document.getElementById('enteredmongo').innerText = 'DATABASE_URI=' + this.value;">


### Step 5 - Choose a Logviewer Name

Choose a memorable name for your Logviewer. You will be provided a log URL under our **.modmail.dev** domain name. You can choose anything you like (with a few restrictions), if you feel it's reasonable, then most likely we do too! Note: only 3-16 alphanumberic characters allowed.

Format (replace **yourchosenname** with your desired name): `https://yourchosenname.modmail.dev/`

**Logviewer Name:** <input id="logviewer" oninput="document.getElementById('enteredlogviewer').innerText = 'LOG_URI=' + this.value;">


### Step 6 - Collecting Data

Congrats! That should be everything we need. If you filled in all the input boxes, there should be 4-5 lines of data generated between **START** and **END**.

`======== START ========`<br>
<code id="enteredlogviewer"></code><br>
<code id="enteredtoken"></code><br>
<code id="enteredmongo"></code><br>
<code id="enteredguild"></code><br>
<code id="enteredstaffguild"></code><br>
`========= END =========`

If it appears to be correct, send everything in between back to the Patreon Modmail DM and you're done!

If it appears to be empty or less than 4 lines between **START** and **END**, then you'll need to make sure you send the following:
- Bot Token
- MongoDB Connection String (with the `<password>` correctly substituted)
- Guild ID (and staff guild ID if applicable)
- Chosen Logviewer Name Under **.modmail.dev**
