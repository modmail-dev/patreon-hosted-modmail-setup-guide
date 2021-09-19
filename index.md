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

Paste your token here (this site is static–nothing is stored and no data is sent to any servers. Unless your browser is hacked, you're perfectly safe to paste your token here):

<div>
  <input id="token">Token: </input>
</div>
