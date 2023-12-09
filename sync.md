# Administration
## Synopsis:
Synchronizing objects, object variables, and whatnot
## Code documentation
### Prelude
```gml
enum NET_SYNC_OWNER {
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
