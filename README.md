# Moonstone [![NPM version](https://img.shields.io/npm/v/moonstone-wrapper.svg?style=flat-square&color=informational)](https://npmjs.com/package/moonstone-wrapper)

A simple, standalone, [dogehouse.tv](https://dogehouse.tv/) API wrapper

<!-- GETTING STARTED -->

## Installing

You will need NodeJS and NPM. To install moonstone on your local project, run:

```
npm install --no-optional --production moonstone-wrapper
```

**If you need audio support, remove the `--no-optional`.**

<!-- USAGE EXAMPLES -->

## Usage

You can use the example from below to see how you can use moonstone.

## Ping Pong Example

```js
const Moonstone = require("moonstone-wrapper");

var bot = Moonstone("TOKEN"); // Replace TOKEN with your bot account's token

bot.on("ready", async () => {
  // When the bot is ready
  console.log(`Ready! Logged in as ${bot.user.username}`); // Log "Ready!"
  const topRooms = await bot.getTopRooms(); // Grab the top rooms
  bot.joinRoom(topRooms[0]); // Join the top room
});

bot.on("newChatMsg", (msg) => {
  // When a message is created
  if (msg.content === "!ping") {
    // If the message content is "!ping"
    msg.room.sendChatMessage("Pong!"); // Send a message in the same channel with "Pong!"
  } else if (msg.content === "!pong") {
    // Otherwise, if the message is "!pong"
    msg.user.sendWhisper("Ping!"); // Whisper to the user with "Ping!"
  }
});

bot.connect(); // Get the bot to connect to Dogehouse
```

More examples can be found in [the examples folder](https://github.com/fuwwy/moonstone/tree/main/docs/examples).

- [Welcomer Example](https://github.com/fuwwy/moonstone/blob/main/docs/examples/welcomer.js)
- [Music Example](https://github.com/fuwwy/moonstone/blob/main/docs/examples/music.js)

## Support

You can find help on the [official support server](https://discord.gg/hDj42dMhn9).

<!-- LICENSE -->

## License

Distributed under the MIT License. See `LICENSE` for more information.

<!-- If you are a Contributor then add your name to the list below -->

## Contributors

- [fuwwy](https://github.com/fuwwy)
- [Isaiah-Hamilton](https://github.com/Isaiah-Hamilton)
- [1chiSensei](https://github.com/1chiSensei)
- [KhaledCP](https://github.com/KhaledCP/)
