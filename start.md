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
 - [Analytics](https://kenanyazbeck.com/netgm2/analytics)
## Getting started
### Notes for later
#### The `_reliable` parameter in a function means whether it is okay to miss packets (`false`) and save up resending or if it is imperative that the packet arrives (`true`)
## Initialization
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
  discord: DiscordStruct {
    app_id: string,
    custom_presence: bool /* Whether you want to use the built in NetGM2 presence or want to use your own code, needs _NekoPresence_ */
  }
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
