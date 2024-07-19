### [< BACK](start.md)

# Event Listener
## Prelude
```diff
+++ All event macros

-// Net state updates
+net_ev_state_update

-// Player updates
+net_ev_join
+net_ev_leave
+net_ev_player_join
+net_ev_player_left

-// Chat updates
+net_ev_chat

-// Global state updates
+net_ev_gstate_update

-// Player prop updates
+net_ev_player_props_update

-// Rpc updates
+net_ev_rpc_call

-// Sound updates
+net_ev_sound_played

-// Net stream updates
+net_ev_stream_created
+net_ev_stream_destroyed
+net_ev_stream_data

-// Other...
+net_ev_destroy_basic
+net_ev_p2p

+net_ev_packet

+net_ev_other_roomchange
```
## Synopsis:
An event system where you can listen to specific events and run code between actions, it is not asynchronous
## Code documentation
```gml
/*
  Attaches a callback to the specified event (you can attach multiple callbacks to the same event)
*/
function net_add_event_listener(_event_name, _callback) -> N/A
```