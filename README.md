<p align="center">
  <img src="assets/logo.png" width="180" height="180">
  <h1 align="center">The Geeks Bot</h1>
</p>
The Geeks is a Telegram bot made to help admins manage their groups.

Initially created to moderate [The Geeks Network](https://t.me/thegeeksnetwork).

**NOTE: The Geeks is in beta phase;**
**it has known issues, but it's successfully being used in production**

## Table of Contents
* [Key Features](#key-features)
* [Setup](#setup)
* [Commands](#commands)
* [Plugins](#plugins)
* [Support](#support)
* [License](#license)

## Key Features
* Synchronized across multiple groups.
* Adding admins to the bot.
* Auto-remove and warn channels and groups ads.
* Kick bots added by users.
* Warn and ban users to control the group.
* Commands work with replying, mentioning and ID.
* Removes commands and temporary bot messages.
* Ability to create custom commands.
* Supports plugins.

Overall, keeps the groups clean and healthy to use.

## Setup
You need [Node.js](https://nodejs.org/) (>= 12) to run this bot.

1. Create a bot via [@BotFather](https://t.me/BotFather) and grab a **token**.
2. Clone this repository
3. Install dependencies via `npm install`.
4. Copy `example.config.js` to `config.js` and edit it.
5. Start the bot via `npm start`.

### Setup with Docker
You need to have [docker](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-from-a-package) installed on your machine.

1. Create a bot via [@BotFather](https://t.me/BotFather) and grab a **token**.
2. Clone this repository
3. Copy `example.config.js` to `config.js` and edit it.
4. Run `docker build -t TheGeeksBot .` to build image.
5. Run `docker run -v $(pwd)/data:/app/data --rm -itd TheGeeksBot` to start the bot.

Now you can add the bot as **administrator** to your groups.

## Commands
Command                 | Role       | Available at | Description
----------------------- | ---------- | ------------ | -----------------
`/admin`                | _Master_   | _Everywhere_ | Makes the user admin in the bot and groups.
`/unadmin`              | _Master_   | _Everywhere_ | Demotes the user from admin list.
`/leave <name\|id>`     | _Master_   | _Everywhere_ | Make the bot to leave the group cleanly.
`/hidegroup`            | _Master_   | _Groups_     | Revoke invite link and hide the group from `/groups` list.
`/showgroup`            | _Master_   | _Groups_     | Make the group accessible via `/groups` list.
`/del [reason]`         | _Admin_    | _Everywhere_ | Deletes replied-to message.
`/warn <reason>`        | _Admin_    | _Groups_     | Warns the user.
`/unwarn`               | _Admin_    | _Everywhere_ | Removes the last warn from the user.
`/nowarns`              | _Admin_    | _Everywhere_ | Clears warns for the user.
`/permit`               | _Admin_    | _Everywhere_ | Permits the user to advertise once, within 24 hours.
`/ban <reason>`         | _Admin_    | _Groups_     | Bans the user from groups.
`/unban`                | _Admin_    | _Everywhere_ | Removes the user from ban list.
`/user`                 | _Admin_    | _Everywhere_ | Shows the status of the user.
`/addcommand <name>`    | _Admin_    | _In-Bot_     | Create a custom command.
`/removecommand <name>` | _Admin_    | _In-Bot_     | Remove a custom command.
`/staff`                | _Everyone_ | _Everywhere_ | Shows a list of admins.
`/link`                 | _Everyone_ | _Everywhere_ | Shows the current group's link.
`/groups`               | _Everyone_ | _Everywhere_ | Shows a list of groups which the bot is admin in.
`/report`               | _Everyone_ | _Everywhere_ | Reports the replied-to message to admins.
`/commands`             | _Everyone_ | _In-Bot_     | Shows a list of available commands.
`/help` \| `/start`     | _Everyone_ | _In-Bot_     | How to use the bot.

All commands and actions are synchronized across all of the groups managed by the owner and they work with **replying**, **mentioning** or **ID** of a user.

If used by reply, `/ban` and `/warn` would remove the replied-to message.

## Plugins

The Geeks is extensible in form of plugins where custom features and commands can be easily added to it. To use a plugin, put it in the [/plugins](/plugins) directory and add its name to plugins array in config.js.
Checkout our [Plugins' Wiki](https://github.com/swatv3nub/TheGeeksBot/wiki/Plugins) page for more information.

**Known plugins**:

* [Captcha](https://gist.github.com/poeti8/d84dfc4538510366a2d89294ff52b4ae): Adds a simple captcha to the bot to kick spam bots on join.
* [Banfiles](https://gist.github.com/poeti8/133796200d66049c9bd58e6265a52f68): Ban users that send files with specified extentions.
* [Anti Arabic](https://gist.github.com/poeti8/966ccef35d61ad2735dc0120ce3e8760): Bans users that send an Arabic/Persian message.
* [Anti X-POST](https://gist.github.com/poeti8/c3057f973466676ca8dbbb1183cd0624): Removes same messages sent by user across one or multiple groups.

## Support

If you need help with using the Bot or setting it up, join our [Support Chat](https://t.me/geekyboychat).

The bot is still in beta phase so feel free to [open issues](https://github.com/swatv3nub/TheGeeksBot/issues/new) and ask for features.

## License

> Important Note: Under the AGPL-3.0 license, if you're running your own instance, you should add a link to the source [(this repository)](https://github.com/swatv3nub/TheGeeksBot) in your bot's bio. If you're modifying this source and making your own bot, you should link to the source of your own version of the bot according to the AGPL-3.0 license. Check [LICENSE](LICENSE) for more info.

---
