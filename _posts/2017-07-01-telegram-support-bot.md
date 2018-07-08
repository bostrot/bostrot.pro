---
layout: post
title: "Telegram Support Bot"
description: "A support bot for the messenger Telegram built on top of the Telegraf framework."
thumb_image: "documentation/sample-image.jpg"
tags: [telegram, nodejs]
---

{% include image.html path="thumbnails/thumbnail_telegram_support_bot.png" path-detail="thumbnails/thumbnail_telegram_support_bot.png" alt="Telegram Support Bot" %}

[Download it here!](https://github.com/bostrot/telegram-support-bot)

#### Features:
  - Manage another bot.
  - Custom support ticket system.
  - Includes a FAQ.
  - Spam protection.
  - Image forwarding.
  - Anonymous & safe support.
  - And more.

#### Integrations
  - [NodeJS](https://nodejs.org/en/)
  - [Telegraf](https://github.com/telegraf/telegraf/)

<hr>

<table>
<tr>
<th>[![Bot API Version](https://img.shields.io/badge/Bot%20API-v3.1-f36caf.svg?style=flat-square)](https://core.telegram.org/bots/api)</th>
<th>[![NPM Version](https://img.shields.io/npm/v/telegraf.svg?style=flat-square)](https://www.npmjs.com/)</th>
<th>[![node](https://img.shields.io/node/v/telegraf.svg?style=flat-square)](https://www.npmjs.com/package/)</th>
<th>[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square)](http://standardjs.com/)
</th>
</tr>
</table>

<table>
<tr>
<th><img src="https://puu.sh/wyvPd/8dde465527.jpg" /></th>
<th><img src="https://puu.sh/wyvxD/35a3b70290.jpg" /></th>
</tr>
</table>

#### Documentation

`telegram-support-bot` was built on top of [`Telegraf`](https://github.com/telegraf/telegraf) libary.

[Telegraf documentation](http://telegraf.js.org).

#### Installation

Install Node ( > 6.2 ) and npm ( > 5 ).

{% highlight js %}
git clone https://github.com/bostrot/telegram-support-bot.git
cd telegram-support-bot
sudo bash setup
{% endhighlight %}

Without setup
{% highlight js %}
npm install telegraf
npm install cron
git clone https://github.com/bostrot/telegram-support-bot.git
cd telegram-support-bot
sudo bash setup 
{% endhighlight %}

Enter the bot location (ex. /home/bots/mybot.js) when asked and then your bot name (ex. mybot)
`setup` will create two systemctl links in order that your bot will be automatically restarted when it crashes and runs in the background.

#### Configuration

You can get your ID with /id. The first number will be yours the second the one from the group you are in (if you are in one; including the minus).

You need to set your bot token and chat ids in `bin/support.js`:

{% highlight js %}
/* edit below */
const bot = new Telegraf("BOT_TOKEN_SUPPORT_BOT") // support bot
var staff_chat = "SUPPORT_STAFF_GROUP_ID" // telegram staff group chat id
var owner_id = "OWNER_ID" // telgram owner id
var supported_bot = "service_name" // service name of the supported bot
var startCommandText = "Welcome in our support chat! Ask your question here."
var faqCommandText = "Check out our FAQ here: Address to your FAQ"
/* edit end */
{% endhighlight %}

## Features

When a user sends a message to the support chat it will create a ticket which will be forwarded to the staff group. Any admin in the staff group may answer that ticket by just replying to it. Salutation is added automatically. Photos will be forwared too.

Currently the support chat offers these commands (staff commands):
* `/open` - lists all open tickets (messages where noone has replied yet)
* `/close` - close a ticket manually (in case someone writes 'thank you')
* `/id (userid)` - lists some stuff from the database about the user

User commands:
* `/start` - tells the user how to use this bot
* `/faq` - shows the FAQ

Admin/Owner commands:
* `/root` - Starts the listener and prevents the bot from crashing (restarts it and sends the log into the staff chat); Also this will open up a dashboard where the admin/owner can control the bot with following `Update`, `Restart`, `Log`, `Stop`.

<img src="https://puu.sh/wywe5/a4c3cee0b7.png" width="400" height="400" />

#### Telegram token

To use the [Telegram Bot API](https://core.telegram.org/bots/api), 
you first have to [get a bot account](https://core.telegram.org/bots) 
by [chatting with BotFather](https://core.telegram.org/bots#6-botfather).

BotFather will give you a *token*, something like `123456789:AbCdfGhIJKlmNoQQRsTUVwxyZ`.

#### Creating a bot

[Telegraf bot framework](https://github.com/telegraf/telegraf) for building a bot

#### Hosting

Get 10$ in credits when you sign up with <a href="https://m.do.co/c/863818fa5312">this code</a> on DigitalOcean. Which is worth 3 months of vServer.
