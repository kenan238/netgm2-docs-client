# Welcome to NetGM2!
## An advanced networking extension for Gamemaker
### Table of contents
 - [Administration](administration.md)
 - [Chat system](chat.md)
 - [Event listeners](eventlistener.md)
 - [File system](file.md)
 - [Global gamestate](gamestate.md)
 - [Peer to peer messages](p2p.md)
 - [Remote Procedural Calls](rpc.md)
 - [Remote sounds](sound.md)
 - [Spawning](spawnbasic.md) & [Syncing objects](sync.md)
 - [Player datastructure & functions](player.md)
 - [Streaming data](stream.md)
 - [Voice chat](voice.md)
 - [Debugging](debug.md)
 - [Steam Integration](steam.md)
## Getting started
### Notes for later
#### The `_reliable` parameter in a function means whether it is okay to miss packets (`false`) and save up resending or if it is imperative that the packet arrives (`true`)
#### Functions that start with two underscores are not meant to be used and are internal functions
## Initialization
### Prelude
Add the `obj_net_web` object to your game's startup room

Call the `net_init` function.

Get a NetGM2 application key and analytics page
### Interlude
Whenever you want to create a connection to a server, use
```gml
net_connect(_ip, _port)
```
Before that, you need to configure netgm2, call `net_set_config`, it goes like so:
```gml
net_set_config({
  timeout: number, /* of milliseconds until we time out */
  p2p_handler: function, /* Gets called whenever you receive a p2p message, arguments being: callback(_recipient_id, _data) */
  uses_accounts: bool, /* Does the server use an account system? */
  uses_files: bool /* Does the server have custom resources that need to be downloaded automatically on connect? */
})
```
```gml
/*
  Make sure to set the player's name!
*/
net_set_name("...")
/*
  Set a password if you use the account system
*/
net_set_password("...")
```
### If you use the MultiClient extension
```gml
// Call this
net_multiclient()
```
### How can I see what NetGM2's state is?
```gml
enum NET_STATE 
{
	CONNECTING,
	CONNECTED,
	REGISTERED,
	DISCONNECTED,
}

function net_get_state() -> NET_STATE
```
### How can I get the server's name?
```gml
function net_get_server_name() -> string
```