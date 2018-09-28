# ShortcutsPreview

A multiplatform bot for showing the details of Shortcuts when linked by their iCloud URL.

## Setup

You need to make a `config.json` in the root. Each service (such as `reddit` or `discord`) will have its own object for settings applying to that service, along with `global`: For example:

```json
{
    "global": {
        "enabled": true
    },
    "reddit": {
        "credentials": {
            "clientId": "h4yk4m821",
            "clientSecret": "It's a secret to everybody."
        }
    },
    "discord": {
        "token": "insertyourtokenhere"
    }
}
```

### Global

Global configuration applies to all services unless that service overrides it.

Since `global.enabled` is `true`, `reddit.enabled` and `discord.enabled` are also `true`. If you set `discord.enabled` to `false` as well, every service except Discord will start.

## Usage

After starting the script, you can use it in Reddit and Discord, depending on if the service was properly set up. There are also hosted versions available.

### Reddit

Allow the Reddit bot to detect posts by inviting the bot to the moderation team. It only uses the `posts` permission since it only needs it to sticky its preview comment, but it will work with no moderator permissions. The hosted version is [u/ShortcutsPreview](https://www.reddit.com/user/ShortcutsPreview/).

Link posts with a iCloud URL linking to a shortcut will be previewed, in the form of a possibly-stickied comment.

### Discord

The Discord bot needs three permissions to work:

* Read Messages
* Send Messages
* Send Links

You can invite the hosted version with the necessary permissions through [this link](https://discordapp.com/api/oauth2/authorize?client_id=492797846265921548&permissions=19456&scope=bot).

The first iCloud URL found in a message is previewed with an embed message.
