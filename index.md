## Thank you for hosting with us!

Welcome to Modmail hosting! Before we can start hosting your new Modmail bot, we will need some bot info from you: a Discord bot token, an external MongoDB database, and some other minor things. This way, you will be the true owner of your Discord bot, and you will have control over the stored data. By the end of this guide, we will have generated everything we need for bot hosting.

If you're already running **an existing Modmail bot** and want to transfer it over: [click here](/transfer.html).

### Getting Started

#### What you'll need:
 - An internet connection and browser.
 - An email account.
 - 5-15 minutes of your time.

There will be multiple input boxes throughout this page, please fill them out as you complete this guide. This website is fully static—meaning everything is only temporarily stored in your browser. <br><u>Keep a copy of everything you paste here, since the input boxes will be cleared if your browser crashes or reloads.</u>

**Please follow every step carefully! Every detail is important in the setup process.**


### Step 1 - Creating Discord Bot Account

You will need to create a bot application, this is how you make a new Discord bot account. Head over to the [Applications Page](https://discord.com/developers/applications/){: target="_blank" rel="noopener"}. Log in (if you've not already) and click on **New Application**. Give your bot a username and click **Create** to register your bot. 

![Discord New Application](/assets/image/step1-1.png)

You are able to customize your bot's profile picture and banner (Bot -> icon/banner) and the About Me section (General Information -> description). After customizing your bot, go to the **Installation** tab, <u>disable</u> **User Install**, and set **Install Link** to **None**.

![Discord Installation settings](/assets/image/step1-2.png)

Next, navigate to the **Bot** tab, scroll down and <u>disable</u> **Public Bot** and <u>enable</u> both **Server Members Intent** and **Message Content Intent**. Don't forget to press the green **Save Changes** button!

![Discord Bot Settings](/assets/image/step1-3.png)

Lastly, we need to grab the bot's token (aka. your bot's login credentials). Scroll to the top of the page, and click **Reset Token** and then **copy the token**.

**Make sure to keep the token private. Anyone who has it can control (or "hack") your bot and abuse your server. If you feel that your token has been leaked, click on `Reset Token` to invalidate the old one and create a new bot token (you'll need to send us your new token if you ever click reset token).**

Example token format (shortened): `abcdefg.abcde.abcdefg12345`

Paste your token that you copied here:

**Token:** <input id="token" oninput="document.getElementById('enteredtoken').innerText = 'TOKEN=' + this.value; document.getElementById('invitelink').href = document.getElementById('invitelink').innerText = 'https://discord.com/oauth2/authorize?scope=bot&integration_type=0&scope=applications.commands+bot&permissions=533381770488&client_id=' + atob(this.value.split('.')[0]);">


### Step 2 - Inviting Your Discord Bot

Click on the following invite link to invite your bot and follow the Discord prompt. All permissions except for **Administrator** is <u>required</u>! We recommend allowing **Administrator** if you struggle with Discord's permission system.

**Invite link:** <a target="_blank" rel="noopener" id="invitelink">Invalid</a>
(If you don't see an invite link or it says invalid, or if the link doesn't work, then it means you didn't input your token correctly on the previous step, or your browser is out of date. [Click here](/get-invite.html) to manually make an invite link.)

After the bot's invited to your server, you will see the bot offline in the members list—that is perfectly normal! It will come online when hosting starts.


### Step 3 - Find Your Server ID

Please enter the ID of your server. If you're unsure where to find the server ID, Discord provides a short guide to help you: [https://dis.gd/FindMyID](https://dis.gd/FindMyID){: target="_blank" rel="noopener"}!

**Server ID:** <input id="guild" oninput="document.getElementById('enteredguild').innerText = 'GUILD_ID=' + this.value;">

**Optional, separate server setup:** if you operate a large community and uses a separate staff-only server (in addition to your public server), Modmail supports that too! Users can see the Modmail bot from the public server, DM the bot, and then Modmail will create the threads in your staff server. Invite Modmail to <u>both</u> servers using the same invite link from **Step 2** (Modmail doesn't need any special permissions in the public server). You can supply your staff server ID here:

**Staff-Only Server ID (optional):** <input id="staffguild" oninput="if (!this.value){document.getElementById('enteredstaffguild').innerText = ''; document.getElementById('enteredstaffguild').style['display'] = 'none'; document.getElementById('staffguildbr').style['display'] = 'none';} else {document.getElementById('enteredstaffguild').innerText = 'MODMAIL_GUILD_ID=' + this.value; document.getElementById('enteredstaffguild').style.removeProperty('display'); document.getElementById('staffguildbr').style.removeProperty('display');}">


### Step 4 - Creating a MongoDB Database

Modmail stores all configurations and logs in MongoDB, and you are required to provide a MongoDB connection string for your bot. [MongoDB Atlas](https://www.mongodb.com/products/platform/atlas-database){: target="_blank" rel="noopener"} provides a free 500MB tier, which is more than enough to store around 3 million message logs. Due to security concerns, we do not provide hosting for your data.

### Sign Up

[Sign-up for an account](https://www.mongodb.com/cloud/atlas/register){: target="_blank" rel="noopener"} and verify your email. 

On the following page, click **Skip Personalization** (these questions do not matter). 

![MongoDB Personalization Questions](/assets/image/step4-1.png)

Next, you will be prompted to deploy your cluster. Choose the **free** option, then select any provider and region: us-west / us-central is preferred, but anything is fine. The cluster name can be anything. **<u>Disable</u> both quick setup options!**

![MongoDB Deploy Cluster](/assets/image/step4-2.png)

### Quick Setup

You should now see a quick setup pop-up window asking you to add connection IP address and create a database user.

#### IP Address Whitelist

Choose **Allow Access from Everywhere**, it will autofill `0.0.0.0/0` under IP address (don't change this), click **Add IP Address** to save.

![Whitelist IP](/assets/image/step4-3.gif)

#### Create Database User

Under username: type `modmail`, and under password: type a random password with **only letters and numbers** (don't use symbols!).  <u>You will need to share us this password so don't make it personal.</u> Click **Create Database User** to save.

![Create user](/assets/image/step4-4.gif)

#### Retrieve the Database Connection String

The next step is to choose a connection method. Click **Drivers** and then copy the connection string down below (the driver doesn't matter). 

![Database URI](/assets/image/step4-5.gif)

**Replace the `<db_password>` within the connection string with the password you set when creating the database user!**

Paste your connection string that you copied here (remember to replace `<db_password>` with the database user's password):

**Connection String:** <input id="mongo" oninput="document.getElementById('enteredmongo').innerText = 'DATABASE_URI=' + this.value;">

### Step 5 - Choose a Logviewer Name

Choose a name for your Logviewer. We will provide you with a free log URL under our **.modmail.dev** domain name. You can choose anything you like (with a few restrictions), if you feel it's reasonable, then we most likely do too! Note: only 3-16 alphanumeric characters are allowed.

Format (replace **yourchosenname** with your desired name): `https://yourchosenname.modmail.dev/`

**Logviewer Name:** <input id="logviewer" oninput="document.getElementById('enteredlogviewer').innerText = 'LOG_URI=' + this.value;">

### Step 6 - Collecting Data

Congrats! That should be everything we need. If you filled in all the input boxes, there should be 4-5 lines of data generated between **START** and **END**.

`======== START ========`<br>
<code id="enteredlogviewer"></code><br>
<code id="enteredtoken"></code><br>
<code id="enteredmongo"></code><br>
<code id="enteredguild"></code><br>
<code id="enteredstaffguild" style="display:none;"></code><br id="staffguildbr" style="display:none;">
`========= END =========`

If it appears to be correct, send everything in between **START** and **END** back to the Patreon Modmail DM and you're done!

If it appears to be empty or less than 4 lines between **START** and **END**, then you'll need to make sure you send the following to the Patreon Modmail DM:
- Bot Token
- MongoDB Connection String (with the `<password>` correctly substituted)
- Guild ID (and staff guild ID if applicable)
- Your Chosen Logviewer Name Under **.modmail.dev**

There you go! You should be all set :D


### What's Next?

After sending all the details back to the Patreon Modmail DM, we will validate everything you sent us. This process might take a few hours depends on our availability, so please bear with us while you wait. We will contact you when the bot is running or if there are any problems!


> This guide is written by taku with parts taken from the [Modmail Wiki](https://github.com/kyb3r/modmail/wiki/Installation).<br>
> If you have found any issues with this guide, please report them to me. Thanks ❤️!
