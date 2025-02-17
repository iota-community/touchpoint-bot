# touchpoint-bot

Matchmaking bot to create a channel for specific participants only

usage:  
`!connect @person1 @person2 [...] channel name`

## Requirements:

- Know how to setup a Discord bot, and a Discord bot ID
- Node ≥ 16
- pm2

## Setup

Clone repo  

Rename `src/config.ts.example` to `src/config.ts` and set your `Discord bot token` in `BOT_TOKEN` and `Channel Category ID` in `TOUCHPOINT_CATEGORY`

```
// perms = 268437552
// https://discord.com/api/oauth2/authorize?client_id=[DISCORD BOT ID]&permissions=268437552&scope=bot

export const BOT_TOKEN = ""; //Discord BOT_TOKEN
export const TOUCHPOINT_CATEGORY = ""; //Category ID under which the new channels will be created
export const BASE_ROLES = []; //Should there be a role for verified people (captchabot, etc...) insert the role ID here
```

Install modules and typescript  
`npm i`  
`npm i -g typescript`

Compile  
`tsc`

Start with pm2  
`pm2 start dist/bot.js`

## Troubleshooting

Discord Categories have a limit of 50 channels. Once that limit is reached, create a new private Category and exchange the Category id in the `src/config.ts` file
