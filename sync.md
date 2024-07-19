### [< BACK](start.md)

# Synchronization
## Synopsis:
Synchronizing objects, object variables, and whatnot
## Code documentation
### Prelude
```gml
enum NET_SYNC_OWNER 
{
	NOONE,
	SERVER,
	PLAYER
}
```
### Interlude
```gml
function NetSync( ... ) constructor {
  self.nid: Real;
  self.obj: String that has the same name as the object asset;
  self.inst: Object Instance;
  self.vars: DsMap;

  /* The rest is internal code */
}
```
```gml
/*
  NOTE: _obj is the string of the asset name
  NOTE: this only creates the object after the server receives the request and spawns it
*/
function net_sync_create(_obj) -> N/A
```
```gml
/*
  NOTE: _obj is the string of the asset name
  NOTE: unlike `net_sync_create`, spawns the object instantly, others will have to wait for the server to process it though.
  NOTE: the object doesn't have a particular id during the timespan where the server hasn't actually processed it and created it, and can therefore not be tampered with easily
*/
function net_sync_create_instant(_obj) -> N/A
```
```gml
/*
  NOTE: _nid is the synced object's network id
  NOTE: vars is a list of strings that have the variables's names to be synced
*/
function net_sync_vars_simple(_nid, _vars, _reliable) -> N/A
```
```gml
/*
  Destroys a synced object
*/
function net_sync_destroy(_nid) -> N/A
```
```gml
/*
  Checks if a user owns a synced object with the specified id
*/
function net_owns_sync(_nid) -> bool (also a real internally)
```
```gml
/*
  Returns the owner or noone
*/
function net_sync_owner(_nid) -> PlayerStruct | noone
```
```gml
/*
  Returns the NetSync or noone
*/
function net_sync_get(_nid) -> NetSync | noone
```
## Signal system
You can send "signals" from a client that doesn't own a synced object to the owner, for interactions and such


### Example:
> Player 1 punches player 2's object

> Player 1 sends signal

> Player 2 receives signal and plays animation


### Interlude
```gml
/*
  nid: is the network id
  data: is the information to send over to the owner
  reliable: is a boolean determining if the request should always arrive or if it can be dismissed in exchange for less bandwidth strain
*/
function net_sync_send_signal_from(nid, data, reliable) -> N/A
```
```gml
/*
  nid: is the network id
  handler: callback that takes in the following arguments in this order:
  * from: id of sender
  * data: data passed
  * this: this synced object (self)
*/
function net_sync_set_signal_handler(nid, handler) -> N/A
```
## Variable dependencies
### Synopsis:
Normally, NetGM2 only synchronizes variables that change.

However, when synchronizing **non-reliably**, some updates may be lost.

Sometimes, that is all good, but for some values _(like X and Y position)_, you'd want to update them both if one changes.

You can make a variable _depend_ on another, __if the dependency updates__, the __variable will update with it__.
### Interlude:
```gml
/*
  _sobj: the synced object struct
  _var: the target variable
  dependency: the variable to depend on
  */
function net_sync_add_var_dependency(_sobj, _var, dependency)
```