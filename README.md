<p align="center">
    <a href="https://discord.gg/VKJeg6nvSH">
  <img src="https://i.imgur.com/1XJhQBe.png"/>
    </a>
</p>

## Discord.js Cheatsheet

This guide will go over all of the Discord.js events.  
Make sure you learn from this, I don't suggest copy pasting.  

## Content:
- Channel events:
  -  channelCreate
  -  channelDelete
  -  channelPinsUpdate
  -  channelUpdate
- Client User events:
  - clientUserGuildSettingsUpdate
  - clientUserSettingsUpdate
- Debug events:
  - debug
- WebSocket events:
  - disconnect
  - reconnecting
  - resume

---

## Channel events:

// channelCreate
// Emitted whenever a channel is created.
// PARAMETER    TYPE        DESCRIPTION
// channel      Channel     The channel that was created

```js
client.on("channelCreate", function(channel){
    console.log(`channelCreate: ${channel}`);
});
```

// channelDelete
// Emitted whenever a channel is deleted.
// PARAMETER   TYPE      DESCRIPTION
// channel     Channel   The channel that was deleted

```js
client.on("channelDelete", function(channel){
    console.log(`channelDelete: ${channel}`);
});
```

// channelPinsUpdate
// Emitted whenever the pins of a channel are updated. Due to the nature of the WebSocket event, not much information can be provided easily here - you need to manually check the pins yourself.
// PARAMETER    TYPE         DESCRIPTION
// channel      Channel      The channel that the pins update occurred in
// time         Date         The time of the pins update

```js
client.on("channelPinsUpdate", function(channel, time){
    console.log(`channelPinsUpdate: ${channel}:${time}`);
});
```
    
// channelUpdate
// Emitted whenever a channel is updated - e.g. name change, topic change.
// PARAMETER        TYPE        DESCRIPTION
// oldChannel       Channel     The channel before the update
// newChannel       Channel     The channel after the update

```js
client.on("channelUpdate", function(oldChannel, newChannel){
    console.log(`channelUpdate -> a channel is updated - e.g. name change, topic change`);
});
```

---

// clientUserGuildSettingsUpdate
// Emitted whenever the client user's settings update.
// PARAMETER                  TYPE                       DESCRIPTION
// clientUserGuildSettings    ClientUserGuildSettings    The new client user guild settings

```js
client.on("clientUserGuildSettingsUpdate", function(clientUserGuildSettings){
    console.log(`clientUserGuildSettingsUpdate -> client user's settings update`);
});
```

// clientUserSettingsUpdate
// Emitted when the client user's settings update.
// PARAMETER             TYPE                  DESCRIPTION
// clientUserSettings    ClientUserSettings    The new client user settings

```js
client.on("clientUserSettingsUpdate", function(clientUserSettings){
    console.log(`clientUserSettingsUpdate -> client user's settings update`);
});
```

// debug
// Emitted for general debugging information.
// PARAMETER    TYPE         DESCRIPTION
// info         string       The debug information

```js
client.on("debug", function(info){
    console.log(`debug -> ${info}`);
});
```

// disconnect
// Emitted when the client's WebSocket disconnects and will no longer attempt to reconnect.
// PARAMETER    TYPE              DESCRIPTION
// Event        CloseEvent        The WebSocket close event

```js
client.on("disconnect", function(event){
    console.log(`The WebSocket has closed and will no longer attempt to reconnect`);
});
```

// emojiCreate
// Emitted whenever a custom emoji is created in a guild.
// PARAMETER    TYPE          DESCRIPTION
// emoji        Emoji         The emoji that was created

```js
client.on("emojiCreate", function(emoji){
    console.log(`a custom emoji is created in a guild`);
});
```

// emojiDelete
// Emitted whenever a custom guild emoji is deleted.
// PARAMETER    TYPE         DESCRIPTION
// emoji        Emoji        The emoji that was deleted

```js
client.on("emojiDelete", function(emoji){
    console.log(`a custom guild emoji is deleted`);
});
```

// emojiUpdate
// Emitted whenever a custom guild emoji is updated.
// PARAMETER    TYPE       DESCRIPTION
// oldEmoji     Emoji      The old emoji
// newEmoji     Emoji      The new emoji

```js
client.on("emojiUpdate", function(oldEmoji, newEmoji){
    console.log(`a custom guild emoji is updated`);
});
```

// error
// Emitted whenever the client's WebSocket encounters a connection error.
PARAMETER    TYPE     DESCRIPTION
error        Error    The encountered error

```js
client.on("error", function(error){
    console.error(`client's WebSocket encountered a connection error: ${error}`);
});
```

// guildBanAdd
// Emitted whenever a member is banned from a guild.
// PARAMETER    TYPE          DESCRIPTION
// guild        Guild         The guild that the ban occurred in
// user         User          The user that was banned

```js
client.on("guildBanAdd", function(guild, user){
    console.log(`a member is banned from a guild`);
});
```

// guildBanRemove
// Emitted whenever a member is unbanned from a guild.
// PARAMETER    TYPE         DESCRIPTION
// guild        Guild        The guild that the unban occurred in
// user         User         The user that was unbanned

```js
client.on("guildBanRemove", function(guild, user){
    console.log(`a member is unbanned from a guild`);
});
```

// guildCreate
// Emitted whenever the client joins a guild.
// PARAMETER    TYPE         DESCRIPTION
// guild        Guild        The created guild

```js
client.on("guildCreate", function(guild){
    console.log(`the client joins a guild`);
});
```

// guildDelete
// Emitted whenever a guild is deleted/left.
// PARAMETER    TYPE         DESCRIPTION
// guild        Guild        The guild that was deleted

```js
client.on("guildDelete", function(guild){
    console.log(`the client deleted/left a guild`);
});
```

// guildMemberAdd
// Emitted whenever a user joins a guild.
// PARAMETER     TYPE               DESCRIPTION
// member        GuildMember        The member that has joined a guild

```js
client.on("guildMemberAdd", function(member){
    console.log(`a user joins a guild: ${member.tag}`);
});
```

// guildMemberAvailable
// Emitted whenever a member becomes available in a large guild.
// PARAMETER     TYPE               DESCRIPTION
// member        GuildMember        The member that became available

```js
client.on("guildMemberAvailable", function(member){
    console.log(`member becomes available in a large guild: ${member.tag}`);
});
```

// guildMemberRemove
// Emitted whenever a member leaves a guild, or is kicked.
// PARAMETER     TYPE               DESCRIPTION
// member        GuildMember        The member that has left/been kicked from the guild

```js
client.on("guildMemberRemove", function(member){
    console.log(`a member leaves a guild, or is kicked: ${member.tag}`);
});
```

// guildMembersChunk
// Emitted whenever a chunk of guild members is received (all members come from the same guild).
// PARAMETER      TYPE                      DESCRIPTION
// members        Array<GuildMember>        The members in the chunk
// guild          Guild                     The guild related to the member chunk

```js
client.on("guildMembersChunk", function(members, guild){
    console.error(`a chunk of guild members is received`);
});
```

// guildMemberSpeaking
// Emitted once a guild member starts/stops speaking.
// PARAMETER     TYPE                DESCRIPTION
// member        GuildMember         The member that started/stopped speaking
// speaking      boolean             Whether or not the member is speaking

```js
client.on("guildMemberSpeaking", function(member, speaking){
    console.log(`a guild member starts/stops speaking: ${member.tag}`);
});
```

// guildMemberUpdate
// Emitted whenever a guild member changes - i.e. new role, removed role, nickname.
// PARAMETER    TYPE               DESCRIPTION
// oldMember    GuildMember        The member before the update
// newMember    GuildMember        The member after the update

```js
client.on("guildMemberUpdate", function(oldMember, newMember){
    console.error(`a guild member changes - i.e. new role, removed role, nickname.`);
});
```

// guildUnavailable
// Emitted whenever a guild becomes unavailable, likely due to a server outage.
// PARAMETER    TYPE          DESCRIPTION
// guild        Guild         The guild that has become unavailable

```js
client.on("guildUnavailable", function(guild){
    console.error(`a guild becomes unavailable, likely due to a server outage: ${guild}`);
});
```

// guildUpdate
// Emitted whenever a guild is updated - e.g. name change.
// PARAMETER     TYPE      DESCRIPTION
// oldGuild      Guild     The guild before the update
// newGuild      Guild     The guild after the update

```js
client.on("guildUpdate", function(oldGuild, newGuild){
    console.error(`a guild is updated`);
});
```

// message
// Emitted whenever a message is created.
// PARAMETER      TYPE           DESCRIPTION
// message        Message        The created message

```js
client.on("message", function(message){
    console.log(`message is created -> ${message}`);
});
```

// messageDelete
// Emitted whenever a message is deleted.
// PARAMETER      TYPE           DESCRIPTION
// message        Message        The deleted message

```js
client.on("messageDelete", function(message){
    console.log(`message is deleted -> ${message}`);
});
```

// messageDeleteBulk
// Emitted whenever messages are deleted in bulk.
// PARAMETER    TYPE                              DESCRIPTION
// messages     Collection<Snowflake, Message>    The deleted messages, mapped by their ID

```js
client.on("messageDeleteBulk", function(messages){
    console.log(`messages are deleted -> ${messages}`);
});
```

// messageReactionAdd
// Emitted whenever a reaction is added to a message.
// PARAMETER              TYPE                   DESCRIPTION
// messageReaction        MessageReaction        The reaction object
// user                   User                   The user that applied the emoji or reaction emoji

```js
client.on("messageReactionAdd", function(messageReaction, user){
    console.log(`a reaction is added to a message`);
});
```

// messageReactionRemove
// Emitted whenever a reaction is removed from a message.
// PARAMETER              TYPE                   DESCRIPTION
// messageReaction        MessageReaction        The reaction object
// user                   User                   The user that removed the emoji or reaction emoji

```js
client.on("messageReactionRemove", function(messageReaction, user){
    console.log(`a reaction is removed from a message`);
});
```

// messageReactionRemoveAll
// Emitted whenever all reactions are removed from a message.
// PARAMETER          TYPE           DESCRIPTION
// message            Message        The message the reactions were removed from

```js
client.on("messageReactionRemoveAll", function(message){
    console.error(`all reactions are removed from a message`);
});
```

// messageUpdate
// Emitted whenever a message is updated - e.g. embed or content change.
// PARAMETER     TYPE           DESCRIPTION
// oldMessage    Message        The message before the update
// newMessage    Message        The message after the update

```js
client.on("messageUpdate", function(oldMessage, newMessage){
    console.log(`a message is updated`);
});
```

// presenceUpdate
// Emitted whenever a guild member's presence changes, or they change one of their details.
// PARAMETER    TYPE               DESCRIPTION
// oldMember    GuildMember        The member before the presence update
// newMember    GuildMember        The member after the presence update

```js
client.on("presenceUpdate", function(oldMember, newMember){
    console.log(`a guild member's presence changes`);
});
```

// ready
// Emitted when the client becomes ready to start working.

```js
client.on("ready", function(){
    console.log(`the client becomes ready to start`);
	console.log(`I am ready! Logged in as ${client.user.tag}!`);
	console.log(`Bot has started, with ${client.users.size} users, in ${client.channels.size} channels of ${client.guilds.size} guilds.`); 

  	client.user.setActivity("the upright organ");
	client.generateInvite(['SEND_MESSAGES', 'MANAGE_GUILD', 'MENTION_EVERYONE'])
	.then(link => {
		console.log(`Generated bot invite link: ${link}`);
		inviteLink = link;
	});
});
```

// reconnecting
// Emitted whenever the client tries to reconnect to the WebSocket.

```js
client.on("reconnecting", function(){
    console.log(`client tries to reconnect to the WebSocket`);
});
```

// resume
// Emitted whenever a WebSocket resumes.
// PARAMETER    TYPE          DESCRIPTION
// replayed     number        The number of events that were replayed

```js
client.on("resume", function(replayed){
    console.log(`whenever a WebSocket resumes, ${replayed} replays`);
});
```

// roleCreate
// Emitted whenever a role is created.
// PARAMETER    TYPE        DESCRIPTION
// role         Role        The role that was created

```js
client.on("roleCreate", function(role){
    console.error(`a role is created`);
});
```

// roleDelete
// Emitted whenever a guild role is deleted.
// PARAMETER    TYPE        DESCRIPTION
// role         Role        The role that was deleted

```js
client.on("roleDelete", function(role){
    console.error(`a guild role is deleted`);
});
```

// roleUpdate
// Emitted whenever a guild role is updated.
// PARAMETER      TYPE        DESCRIPTION
// oldRole        Role        The role before the update
// newRole        Role        The role after the update

```js
client.on("roleUpdate", function(oldRole, newRole){
    console.error(`a guild role is updated`);
});
```

// typingStart
// Emitted whenever a user starts typing in a channel.

```js
// PARAMETER      TYPE            DESCRIPTION
// channel        Channel         The channel the user started typing in
// user           User            The user that started typing

client.on("typingStart", function(channel, user){
    console.log(`${user.tag} has started typing`);
});
```

// typingStop
// Emitted whenever a user stops typing in a channel.

```js
// PARAMETER       TYPE           DESCRIPTION
// channel         Channel        The channel the user stopped typing in
// user            User           The user that stopped typing

client.on("typingStop", function(channel, user){
    console.log(`${user.tag} has stopped typing`);
});
```

// userNoteUpdate
// Emitted whenever a note is updated.

```js
// PARAMETER      TYPE          DESCRIPTION
// user           User          The user the note belongs to
// oldNote        String        The note content before the update
// newNote        String        The note content after the update

client.on("userNoteUpdate", function(user, oldNote, newNote){
    console.log(`a member's note is updated`);
});
```

### userUpdate
##### Emitted whenever a user's details (e.g. username) are changed.

```js
// PARAMETER      TYPE        DESCRIPTION
// oldUser        User        The user before the update
// newUser        User        The user after the update

client.on("userUpdate", function(oldUser, newUser){
    console.log(`user's details (e.g. username) are changed`);
});
```

### voiceStateUpdate
##### Emitted whenever a user changes voice state - e.g. `joins/leaves a channel, mutes/unmutes`.

```js
// PARAMETER    TYPE             DESCRIPTION
// oldMember    GuildMember      The member before the voice state update
// newMember    GuildMember      The member after the voice state update

client.on("voiceStateUpdate", function(oldMember, newMember){
    console.log(`a user changes voice state`);
});
```

### warn
##### Emitted for general warnings. 

```js
// PARAMETER    TYPE       DESCRIPTION
// info         string     The warning

client.on("warn", function(info){
    console.log(`warn: ${info}`);
});
```

<p align="center">
  <a href="https://discord.gg/VKJeg6nvSH">
  <img src="https://i.imgur.com/HWF3UoH.png"/>
  </a>
</p>
