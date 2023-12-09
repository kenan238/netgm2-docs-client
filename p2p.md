# Administration
## Synopsis:
Peer to peer messages between arbitrary clients
## Code documentation
```gml
/*
  Sends a p2p message to a player
*/
function net_p2p_send(_data, _destination_user_id) -> N/A
```
```gml
/*
  Sends a p2p message to everyone within a room
*/
function net_p2p_send_room(_data) -> N/A
```