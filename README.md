<p align="center">
    <a href="https://discord.gg/MeD6HFx9fG">
  <img src="https://i.imgur.com/RZjyfjG.png"/>
    </a>
</p>

## Discord.js Cheatsheet

This guide will go over all of the Discord.js events and how to use them, along with examples. You can use this information in many ways, but the most common would be creating a log system for your Discord bot. I don't suggest just copy pasting, try implementing this with your own code. Happy reading!

If you want to just copy the code you can do so **[here](https://github.com/armfxl/discord.js-cheatsheet/blob/main/cheatsheet.js)**.

### Content:

- **[Channel Events](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#channel-events)**
  - [channelCreate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#channelCreate)
  - [channelDelete](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#channelDelete)
  - [channelPinsUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#channelPinsUpdate)
  - [channelUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#channelUpdate)
- **[Client User Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#client-user-events)**
  - [clientUserGuildSettingsUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#clientUserGuildSettingsUpdate)
  - [clientUserSettingsUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#clientUserSettingsUpdate)
- **[Debug Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#debug-events)**
  - [debug](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#debug)
- **[Error Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#error-events)**
  - [error](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#error)
  - [warn](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#warn)
- **[WebSocket Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#websocket-events)**
  - [disconnect](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#disconnect)
  - [reconnecting](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#reconnecting)
  - [resume](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#resume)
- **[Emoji Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#emoji-events)**
  - [emojiCreate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#emojiCreate)
  - [emojiDelete](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#emojiDelete)
  - [emojiUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#emojiUpdate)
- **[Guild Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guild-events)**
  - [guildBanAdd](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildBanAdd)
  - [guildBanRemove](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildBanRemove)
  - [guildCreate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildCreate)
  - [guildDelete](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildDelete)
  - [guildUnavailable](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildMemberSpeaking)
  - [guildUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildUpdate)
- **[Guild Member Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guild-events)**
  - [guildMemberAdd](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildMemberAdd)
  - [guildMemberAvailable](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildMemberAvailable)
  - [guildMemberRemove](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildMemberRemove)
  - [guildMembersChunk](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildMembersChunk)
  - [guildMemberUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#presenceUpdate)
  - [presenceUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#guildMemberUpdate)
- **[Interaction Event:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#interacation-event)**
  - [interactionCreate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#interactionCreate)
- **[Message Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#message-events)**
  - [messageCreate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#messageCreate)
  - [messageDelete](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#messageDelete)
  - [messageDeleteBulk](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#messageDeleteBulk)
  - [messageReactionAdd](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#messageReactionAdd)
  - [messageReactionRemove](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#messageReactionRemove)
  - [messageReactionRemoveAll](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#messageReactionRemoveAll)
  - [messageUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#messageUpdate)
  - [typingStart](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#typingStart)
  - [typingStop](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#typingStop)
- **[Client Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#client-events)**
  - [ready](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#ready)
- **[Role Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#role-events)**
  - [roleCreate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#roleCreate)
  - [roleDelete](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#roleDelete)
  - [roleUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#roleUpdate)
- **[User Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#user-events)**
  - [userNoteUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#userNoteUpdate)
  - [userUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#userUpdate)
- **[Voice Events:](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#voice-events)**
  - [voiceStateUpdate](https://github.com/armfxl/discord.js-cheatsheet/blob/main/README.md#voiceStateUpdate)

## Channel Events:

### channelCreate

##### Emitted whenever a channel is created.

```js
// PARAMETER    TYPE        DESCRIPTION
// channel      Channel     The channel that was created

client.on('channelCreate', function (channel) {
	console.log(`channelCreate: ${channel}`);
});
```

### channelDelete

#### Emitted whenever a channel is deleted.

```js
// PARAMETER   TYPE      DESCRIPTION
// channel     Channel   The channel that was deleted

client.on('channelDelete', function (channel) {
	console.log(`channelDelete: ${channel}`);
});
```

### channelPinsUpdate

##### Emitted whenever the pins of a channel are updated. Due to the nature of the WebSocket event, not much information can be provided easily here.

```js
// PARAMETER    TYPE         DESCRIPTION
// channel      Channel      The channel that the pins update occurred in
// time         Date         The time of the pins update

client.on('channelPinsUpdate', function (channel, time) {
	console.log(`channelPinsUpdate: ${channel}:${time}`);
});
```

### channelUpdate

##### Emitted whenever a channel is updated - e.g. name change, topic change.

```js
// PARAMETER        TYPE        DESCRIPTION
// oldChannel       Channel     The channel before the update
// newChannel       Channel     The channel after the update

client.on('channelUpdate', function (oldChannel, newChannel) {
	console.log(`channelUpdate -> a channel is updated - e.g. name change, topic change`);
});
```

## Client User Events:

### clientUserGuildSettingsUpdate

##### Emitted whenever the client user's settings update.

```js
// PARAMETER                  TYPE                       DESCRIPTION
// clientUserGuildSettings    ClientUserGuildSettings    The new client user guild settings

client.on('clientUserGuildSettingsUpdate', function (clientUserGuildSettings) {
	console.log(`clientUserGuildSettingsUpdate -> client user's settings update`);
});
```

### clientUserSettingsUpdate

##### Emitted when the client user's settings update.

```js
// PARAMETER             TYPE                  DESCRIPTION
// clientUserSettings    ClientUserSettings    The new client user settings

client.on('clientUserSettingsUpdate', function (clientUserSettings) {
	console.log(`clientUserSettingsUpdate -> client user's settings update`);
});
```

## Debug Events:

### debug

##### Emitted for general debugging information.

```js
// PARAMETER    TYPE         DESCRIPTION
// info         string       The debug information

client.on('debug', function (info) {
	console.log(`debug -> ${info}`);
});
```

## Error Events:

### error

##### Emitted whenever the client's WebSocket encounters a connection error.

```js
// PARAMETER    TYPE     DESCRIPTION
// error        Error    The encountered error

client.on('error', function (error) {
	console.error(`client's WebSocket encountered a connection error: ${error}`);
});
```

### warn

##### Emitted for general warnings.

```js
// PARAMETER    TYPE       DESCRIPTION
// info         string     The warning

client.on('warn', function (info) {
	console.log(`warn: ${info}`);
});
```

## WebSocket Events:

### disconnect

##### Emitted when the client's WebSocket disconnects and will no longer attempt to reconnect.

```js
// PARAMETER    TYPE              DESCRIPTION
// Event        CloseEvent        The WebSocket close event

client.on('disconnect', function (event) {
	console.log(`The WebSocket has closed and will no longer attempt to reconnect`);
});
```

### reconnecting

##### Emitted whenever the client tries to reconnect to the WebSocket.

```js
client.on('reconnecting', function () {
	console.log(`client tries to reconnect to the WebSocket`);
});
```

### resume

##### Emitted whenever a WebSocket resumes.

```js
// PARAMETER    TYPE          DESCRIPTION
// replayed     number        The number of events that were replayed

client.on('resume', function (replayed) {
	console.log(`whenever a WebSocket resumes, ${replayed} replays`);
});
```

## Emoji Events:

### emojiCreate

##### Emitted whenever a custom emoji is created in a guild.

```js
// PARAMETER    TYPE          DESCRIPTION
// emoji        Emoji         The emoji that was created

client.on('emojiCreate', function (emoji) {
	console.log(`a custom emoji is created in a guild`);
});
```

### emojiDelete

##### Emitted whenever a custom guild emoji is deleted.

```js
// PARAMETER    TYPE         DESCRIPTION
// emoji        Emoji        The emoji that was deleted

client.on('emojiDelete', function (emoji) {
	console.log(`a custom guild emoji is deleted`);
});
```

### emojiUpdate

##### Emitted whenever a custom guild emoji is updated.

```js
// PARAMETER    TYPE       DESCRIPTION
// oldEmoji     Emoji      The old emoji
// newEmoji     Emoji      The new emoji

client.on('emojiUpdate', function (oldEmoji, newEmoji) {
	console.log(`a custom guild emoji is updated`);
});
```

## Guild Events:

### guildBanAdd

##### Emitted whenever a member is banned from a guild.

```js
// PARAMETER    TYPE          DESCRIPTION
// guild        Guild         The guild that the ban occurred in
// user         User          The user that was banned

client.on('guildBanAdd', function (guild, user) {
	console.log(`a member is banned from a guild`);
});
```

### guildBanRemove

##### Emitted whenever a member is unbanned from a guild.

```js
// PARAMETER    TYPE         DESCRIPTION
// guild        Guild        The guild that the unban occurred in
// user         User         The user that was unbanned

client.on('guildBanRemove', function (guild, user) {
	console.log(`a member is unbanned from a guild`);
});
```

### guildCreate

##### Emitted whenever the client joins a guild.

```js
// PARAMETER    TYPE         DESCRIPTION
// guild        Guild        The created guild

client.on('guildCreate', function (guild) {
	console.log(`the client joins a guild`);
});
```

### guildDelete

#### Emitted whenever a guild is deleted/left.

```js
// PARAMETER    TYPE         DESCRIPTION
// guild        Guild        The guild that was deleted

client.on('guildDelete', function (guild) {
	console.log(`the client deleted/left a guild`);
});
```

### guildUnavailable

##### Emitted whenever a guild becomes unavailable, likely due to a server outage.

```js
// PARAMETER    TYPE          DESCRIPTION
// guild        Guild         The guild that has become unavailable

client.on('guildUnavailable', function (guild) {
	console.error(`a guild becomes unavailable, likely due to a server outage: ${guild}`);
});
```

### guildUpdate

##### Emitted whenever a guild is updated - e.g. name change.

```js
// PARAMETER     TYPE      DESCRIPTION
// oldGuild      Guild     The guild before the update
// newGuild      Guild     The guild after the update

client.on('guildUpdate', function (oldGuild, newGuild) {
	console.error(`a guild is updated`);
});
```

## Guild Member Events:

### guildMemberAdd

#### Emitted whenever a user joins a guild.

```js
// PARAMETER     TYPE               DESCRIPTION
// member        GuildMember        The member that has joined a guild

client.on('guildMemberAdd', function (member) {
	console.log(`a user joins a guild: ${member.tag}`);
});
```

### guildMemberAvailable

##### Emitted whenever a member becomes available in a large guild.

```js
// PARAMETER     TYPE               DESCRIPTION
// member        GuildMember        The member that became available

client.on('guildMemberAvailable', function (member) {
	console.log(`member becomes available in a large guild: ${member.tag}`);
});
```

### guildMemberRemove

##### Emitted whenever a member leaves a guild, or is kicked.

```js
// PARAMETER     TYPE               DESCRIPTION
// member        GuildMember        The member that has left/been kicked from the guild

client.on('guildMemberRemove', function (member) {
	console.log(`a member leaves a guild, or is kicked: ${member.tag}`);
});
```

### guildMembersChunk

##### Emitted whenever a chunk of guild members is received (all members come from the same guild).

```js
// PARAMETER      TYPE                      DESCRIPTION
// members        Array<GuildMember>        The members in the chunk
// guild          Guild                     The guild related to the member chunk

client.on('guildMembersChunk', function (members, guild) {
	console.error(`a chunk of guild members is received`);
});
```

### guildMemberUpdate

##### Emitted whenever a guild member changes - i.e. new role, removed role, nickname.

```js
// PARAMETER    TYPE               DESCRIPTION
// oldMember    GuildMember        The member before the update
// newMember    GuildMember        The member after the update

client.on('guildMemberUpdate', function (oldMember, newMember) {
	console.error(`a guild member changes - i.e. new role, removed role, nickname.`);
});
```

### presenceUpdate

##### Emitted whenever a guild member's presence changes, or they change one of their details.

```js
// PARAMETER    TYPE               DESCRIPTION
// oldMember    GuildMember        The member before the presence update
// newMember    GuildMember        The member after the presence update

client.on('presenceUpdate', function (oldMember, newMember) {
	console.log(`a guild member's presence changes`);
});
```

## Interaction Event:

### interactionCreate

##### Emitted when an interaction is created.

```js
// PARAMETER    TYPE               DESCRIPTION
// interaction  Interaction        The interaction which was created

client.on('interactionCreate', function (interaction) {
	console.log(`message is created -> ${interaction}`);
});
```

## Message Events:

### messageCreate

##### Emitted whenever a message is created.

```js
// PARAMETER      TYPE           DESCRIPTION
// message        Message        The created message

client.on('messageCreate', function (message) {
	console.log(`message is created -> ${message}`);
});
```

### messageDelete

##### Emitted whenever a message is deleted.

```js
// PARAMETER      TYPE           DESCRIPTION
// message        Message        The deleted message

client.on('messageDelete', function (message) {
	console.log(`message is deleted -> ${message}`);
});
```

### messageDeleteBulk

##### Emitted whenever messages are deleted in bulk.

```js
// PARAMETER    TYPE                              DESCRIPTION
// messages     Collection<Snowflake, Message>    The deleted messages, mapped by their ID

client.on('messageDeleteBulk', function (messages) {
	console.log(`messages are deleted -> ${messages}`);
});
```

### messageReactionAdd

##### Emitted whenever a reaction is added to a message.

```js
// PARAMETER              TYPE                   DESCRIPTION
// messageReaction        MessageReaction        The reaction object
// user                   User                   The user that applied the emoji or reaction emoji

client.on('messageReactionAdd', function (messageReaction, user) {
	console.log(`a reaction is added to a message`);
});
```

### messageReactionRemove

##### Emitted whenever a reaction is removed from a message.

```js
// PARAMETER              TYPE                   DESCRIPTION
// messageReaction        MessageReaction        The reaction object
// user                   User                   The user that removed the emoji or reaction emoji

client.on('messageReactionRemove', function (messageReaction, user) {
	console.log(`a reaction is removed from a message`);
});
```

### messageReactionRemoveAll

##### Emitted whenever all reactions are removed from a message.

```js
// PARAMETER          TYPE           DESCRIPTION
// message            Message        The message the reactions were removed from

client.on('messageReactionRemoveAll', function (message) {
	console.error(`all reactions are removed from a message`);
});
```

### messageUpdate

##### Emitted whenever a message is updated - e.g. embed or content change.

```js
// PARAMETER     TYPE           DESCRIPTION
// oldMessage    Message        The message before the update
// newMessage    Message        The message after the update

client.on('messageUpdate', function (oldMessage, newMessage) {
	console.log(`a message is updated`);
});
```

### typingStart

##### Emitted whenever a user starts typing in a channel.

```js
// PARAMETER      TYPE            DESCRIPTION
// channel        Channel         The channel the user started typing in
// user           User            The user that started typing

client.on('typingStart', function (channel, user) {
	console.log(`${user.tag} has started typing`);
});
```

### typingStop

##### Emitted whenever a user stops typing in a channel.

```js
// PARAMETER       TYPE           DESCRIPTION
// channel         Channel        The channel the user stopped typing in
// user            User           The user that stopped typing

client.on('typingStop', function (channel, user) {
	console.log(`${user.tag} has stopped typing`);
});
```

## Client Events:

### ready

##### Emitted when the client becomes ready to start working.

```js
client.on('ready', function () {
	console.log(`Logged in as ${client.user.tag}!`);
});
```

## Role Events:

### roleCreate

##### Emitted whenever a role is created.

```js
// PARAMETER    TYPE        DESCRIPTION
// role         Role        The role that was created

client.on('roleCreate', function (role) {
	console.error(`a role is created`);
});
```

### roleDelete

##### Emitted whenever a guild role is deleted.

```js
// PARAMETER    TYPE        DESCRIPTION
// role         Role        The role that was deleted

client.on('roleDelete', function (role) {
	console.error(`a guild role is deleted`);
});
```

### roleUpdate

##### Emitted whenever a guild role is updated.

```js
// PARAMETER      TYPE        DESCRIPTION
// oldRole        Role        The role before the update
// newRole        Role        The role after the update

client.on('roleUpdate', function (oldRole, newRole) {
	console.error(`a guild role is updated`);
});
```

## User Events:

### userNoteUpdate

##### Emitted whenever a note is updated.

```js
// PARAMETER      TYPE          DESCRIPTION
// user           User          The user the note belongs to
// oldNote        String        The note content before the update
// newNote        String        The note content after the update

client.on('userNoteUpdate', function (user, oldNote, newNote) {
	console.log(`a member's note is updated`);
});
```

### userUpdate

##### Emitted whenever a user's details (e.g. username) are changed.

```js
// PARAMETER      TYPE        DESCRIPTION
// oldUser        User        The user before the update
// newUser        User        The user after the update

client.on('userUpdate', function (oldUser, newUser) {
	console.log(`user's details (e.g. username) are changed`);
});
```

### voiceStateUpdate

##### Emitted whenever a user changes voice state - e.g. `joins/leaves a channel, mutes/unmutes`.

```js
// PARAMETER    TYPE             DESCRIPTION
// oldMember    GuildMember      The member before the voice state update
// newMember    GuildMember      The member after the voice state update

client.on('voiceStateUpdate', function (oldMember, newMember) {
	console.log(`a user changes voice state`);
});
```

### Thanks for reading!

Feel free to reach out to me for support.

### By: [armful#0001](https://github.com/armfxl)

<p align="center">
  <a href="https://discord.gg/MeD6HFx9fG">
  <img src="https://i.imgur.com/t2jixCo.png"/>
  </a>
</p>
