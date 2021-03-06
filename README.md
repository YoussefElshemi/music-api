# Doyle Music - A simple module

This module would allow any discord.js bot running on v12.0.0 (master) to have musical functionally.

## Example

```js
const api = require("doyle-music");
const Discord = require("discord.js");
const client = new Discord.Client();

client.login("TOKEN");

new api(client, "YT API KEY", { prefix: "-", anyoneCanSkip: true, autoHandle: true, autoLeaveTime: 30000 });
```

If you wish to use this module by handling the commands yourself, we change the `autoHandle` option to false, here is an example:

```js
const api = require("doyle-music");
const Discord = require("discord.js");
const client = new Discord.Client();
const prefix = "!";

client.login("TOKEN");

const music = new api(client, "YT API KEY", { prefix: "-", anyoneCanSkip: true, autoHandle: false, autoLeaveTime: 30000 });

client.on("message", message => {
  let args = message.content.split(" ");
  const command = args[0].slice(prefix.length);
  args = args.join(" ").slice(command.length + this.prefix.length).trim().split(" ");
  
  if (command === "play") {
      music.play(client, message, args);
  }
})
```

That's all you need to do to get started, but make sure you have ffmpeg and node-opus installed, simply running `npm i node-opus ffmpeg-binaries` will do it!

## Avaiable Options:
| options          | type    | description                                                                                                                              | 
|------------------|---------|------------------------------------------------------------------------------------------------------------------------------------------|
| prefix           | String  | The prefix the music bot should use.                                                                                                     | 
| anyoneCanSkip    | Boolean | Whether or not anyone can skip, if set to false, only Administrators can skip.                                                           | 
| autoHandle       | Boolean | Whether or not the client handles everything for you, if set to false, you can handle commands yourself using the functions documented.  | 
| autoLeaveTime    | Number  | How long to wait untill the client leaves the voice channel automatically if no one is in the call, in milliseconds. Default: 30 seconds.|    
   

## Available commands:
`loop` | loops the current playing stream

`np` | displays the current song in the music queue

`pause` | pauses the current playing stream

`play` | plays a song or adds it to the queue if there is one.

`queue` | displays the music queue.

`remove` | removes a certain song from the queue

`resume` | resumes the current playing stream

`search` | search youtube for a video to play

`skip` | skips the current playing stream

`stop` | stops the current playing stream

`volume` | sets the volume of the stream