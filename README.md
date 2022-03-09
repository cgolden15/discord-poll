# discord.js-qotd													

[![npm](https://img.shields.io/npm/v/discord.js-qotd)](https://www.npmjs.com/package/discord.js-qotd)
[![npm](https://img.shields.io/npm/dt/discord.js-qotd)](https://npm-stat.com/charts.html?package=discord.js-qotd)
[![NPM](https://img.shields.io/npm/l/discord.js-qotd)](https://www.npmjs.com/package/discord.js-qotd)

discord.js-qotd is a Node.js module that allows you to create polls or questions of the day with your discord bot. You can customize the arg separator, emoji and the embed color!

### What's next?:
* v1.6.0 Variable message content to go along with the qotd embed.
* v2.0.0 Discord.js v13 support

## Installation 

<br>

```
npm i discord.js-qotd
```

<br>

## Parameter types

<br>

```JavaScript
poll(message: Discord.Message, args: string[], separator: string, embedColor: Discord.ColorResolvable, emoji: string)
```

### Documentation 

[Discord.Message](https://discord.js.org/#/docs/main/stable/class/Message)

[Discord.ColorResolvable](https://discord.js.org/#/docs/main/stable/typedef/ColorResolvable)

<br>

## Usage example

### Code

```JavaScript
const Discord = require('discord.js');
const { poll } = require('discord.js-qotd');

module.exports = {
	name: 'qotd',
	description: 'Create a qeustion of the day embed.',
	usage: 'Title + Option 1 + Option 2 + Option 3 + etc',
	execute(client, message, args) {
		poll(message, args, '+', '#00D1CD', "🤷‍♂️");
	},
};
```

### On discord

```
!qotd Is this a poll?
```

This will return an embed message with '**Is this a poll?**' as title and with 👍 and 👎 reactions.

![Simple Poll Image]()

<br>

```
!poll message + args1 + args2 + args3
```

This will return an embed message with '**What is your favorite food?**' as title and '*Pasta*', '*Burger*' and '*Pizza*' as fields, with corresponding reactions (🇦 => 🇨).

(If **'+'** is chosed as separator)

<br>

![Poll Image]()

### ⚠️ You cannot add more than 26 options to the poll. 

<br>
<i>Disclaimer: This module was originally created by nicolasmf under the name <a link href="https://www.npmjs.com/package/discord.js-poll"> discord.js-poll</a>. The original code for this plugin was taken from there in accordance with its MIT license. I took on this project due to lack of updates, functionality and v13 support from nicholasmf. 
