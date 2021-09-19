### Creating a Bot Invite

[Go Back](/)

To create an bot invite link, navigate to the **Oauth2** tab in the Discord Developer Portal for your bot, and copy the **Client ID**.

![Copy Client ID](https://i.imgur.com/7NtSmig.png)

Use the following template URL and replace the `XXXXXCLIENTIDXXXXX` at the end with your copied client ID. Don't change anything else!

```https://discord.com/oauth2/authorize?scope=bot&permissions=2953309432&client_id=XXXXXCLIENTIDXXXXX```

Follow the Discord prompt to invite your bot. All permissions excepted for **Administrator** is <u>required</u>! But we recommend allowing **Administrator** for ease of setup and avoid permission complications.

After the bot's invited to your server, you will see the bot offline in the members list—that is perfectly normal! It will come online when we start hosting.


> This guide is written by taku#3343 with parts taken from the [Modmail Wiki](https://github.com/kyb3r/modmail/wiki/Installation).<br>
> If you have found any issues with this guide, please report them to me. Thanks ❤️!
