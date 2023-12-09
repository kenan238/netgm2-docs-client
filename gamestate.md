# Administration
## Synopsis:
A global struct that can be modified from the server and client
## Code documentation
```gml
/*
  Example on how to commit changes to the global gamestate
*/
net_gamestate_begin_change()

with (obj_net) {
  gamestate.state.someproperty = "something";
}

net_gamestate_commit()
```