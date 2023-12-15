### [< BACK](start.md)

# Player
## Synopsis:
Functions for players
## Code documentation
```gml
/*
  Finds a player's index in the obj_net.players array by the player's id
*/
function net_player_find_idx_by_id(_id) -> Real
```
```gml
/*
  Returns a player instance by it's id
*/
function net_player_get(_id) -> PlayerStruct {
  pid: UserId,
  name: string,
  acc_id: AccountId, /* Only works if accounts are enabled */
  props: Struct, /* Shared structure that only the player can modify */
  powlvl: POWER_TYPES, /* Administrative privileges of said player */
}
```
```gml
/*
  Example on how to modify player props
*/
global.net_props.someproperty = "somevalue";

net_commit_props()
```

```gml
/*
  Gets all players
*/
function net_player_find_idx_by_id(_id) -> List<PlayerStruct>
```