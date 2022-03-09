# discord.js-qotd

[![npm](https://img.shields.io/npm/v/discord.js-qotd)](https://www.npmjs.com/package/discord.js-qotd)
[![NPM](https://img.shields.io/npm/l/discord.js-qotd)](https://www.npmjs.com/package/discord.js-qotd)

discord.js-qotd is a Node.js module that allows you to create polls or questions of the day with your discord bot. You can customize the separator and the embed color! This module was originally created by nicolasmf and called [discord.js-poll](https://www.npmjs.com/package/discord.js-poll). However due to lack of updates, and broken functionality I have decided to start updating it myself.

### Features I'm working on:
* d.js v13 support
* Customizable emoji option
* Variable message content to go along with the qotd embed.

## Installation 

<br>

```
npm i discord.js-qotd
```

<br>

## Parameter types

<br>

```JavaScript
poll(message: Discord.Message, args: string[], separator: string, embedColor: Discord.ColorResolvable)
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
		poll(message, args, '+', '#00D1CD');
	},
};
```

### On discord

```
!qotd Is this a poll?
```

This will return an embed message with '**Is this a poll?**' as title and with 👍 and 👎 reactions.

![Simple Poll Image](https://cdn.discordapp.com/attachments/417731712135725066/834428865342472212/unknown.png)

<br>

```
!qotd What is your favorite food? + Pasta + Burgers + Pizza
```

This will return an embed message with '**What is your favorite food?**' as title and '*Pasta*', '*Burger*' and '*Pizza*' as fields, with corresponding reactions (🇦 => 🇨).

(If **'+'** is chosed as separator)

<br>

![Poll Image](https://cdn.discordapp.com/attachments/417731712135725066/834428463616229456/unknown.png)

### ⚠️ You cannot add more than 26 options to the poll. 
