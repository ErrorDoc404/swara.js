## Swara

> A stable and updated wrapper around Lavalink

### Features

✅ Stable

✅ Documented

✅ Updated

✅ QueuSystem

### Installation

> `npm install https://www.github.com/ErrorDoc404/Swara.js.git`

### Documentation

https://swara.karatadharta.xyz

### Small code snippet examples

> Initializing the library (Using Connector Discord.JS)

```js
const { Client } = require("discord.js");
const { Swara, Connectors } = require("swara.js");
const Nodes = [
  {
    name: "Localhost",
    url: "localhost:6969",
    auth: "re_aoharu",
    version: '3' // use 4 if connecting to lavalink v4
  },
];
const client = new Client();
const swara = new Swara(new Connectors.DiscordJS(client), Nodes);

// Always handle "error" events or your program may crash due to uncaught error
swara.on("error", (_, error) => console.error(error));
client.login("token");

// If you want swara to be available on client, then bind it to it, here is one example of it
client.swara = swara;
```

> Never initialize Swara like this, or else she will never initialize, start swara before you call `client.login()`

```js
client.on("ready", () => {
  client.swara = new Swara(new Connectors.DiscordJS(client), Nodes);
});
```