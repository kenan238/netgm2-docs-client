### [< BACK](start.md)

# General functions
## Synopsis:
Base functions that wouldn't belong in their own category.
## Code documentation
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
### Getting the state
```gml
enum NET_STATE 
{
	CONNECTING,   /* Establishing a connection */
	CONNECTED,    /* Connected but not fully loaded */
	REGISTERED,   /* Connected and loaded */
	DISCONNECTED, /* Offline */
}

function net_get_state() -> NET_STATE
```
### Getting the server name
```gml
function net_get_server_name() -> string
```
### Getting the GC workload
```gml
function net_gc_workload() -> real
```
### Adding a custom packet
```gml
/*
  _type is a number corresponding to the packet ID
  _callback is the function that will be called when said packet type is received

  _callback takes in a packet struct, with all the packet data.
*/
function net_add_custom_packet(_type, _callback) -> real
```
### Getting the GC workload
```gml
function net_gc_workload() -> real
```
### Shorthand for comparing network id (Am I this ID or not?)
```gml
function net_iam(n_id) -> boolean
```
### Get a synced object's owner
```gml
/*
  returns -1 if fails
*/
function net_heis(n_id) -> real
```
### Get a static ID for an instance in a room
If an instance has been placed in a room, you can get its __static__ ID, that will not change.
It is the same as the server's `GameMaker.Room.Instance.Order (uint)`, which can help in cross-referencing a room's instance between the _server_ and _client_.

```gml
/*
  _room: room where the instance is located
  _inst_id: instance's id property
*/
function net_get_static_id(_room, _inst_id)
```