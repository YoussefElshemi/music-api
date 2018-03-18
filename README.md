# Doyle Music - A simple module

This module would allow any discord.js bot running on v12.0.0 (master) to have musical functionally.

## Example

```js
const api = require("doyle-music");
const Discord = require("discord.js");
const client = new Discord.Client();

client.login("TOKEN");

new api(client, "YT API TOKEN", { prefix: "-", anyoneCanSkip: false });
```

That's all you need to do to get started, but make sure you have ffmpeg and node-opus installed, simply running `npm i node-opus ffmpeg-binaries` will do it!

## Avaiable Options:
| options       | type    | description                                                                    |  
|---------------|---------|--------------------------------------------------------------------------------|
| prefix        | String  | The prefix the music bot should use.                                           |     
| anyoneCanSkip | Boolean | Whether or not anyone can skip, if set to false, only Administrators can skip. |    

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