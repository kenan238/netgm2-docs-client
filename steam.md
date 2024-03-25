### [< BACK](start.md)

# Steam Layer
## Dependencies:
Gamemaker's Steamworks extension
## Synopsis:
The steam layer is what enables NetGM2 to connect to/create steam lobbies and transfer packets through Steam.
## Usage:
# !! NOTE: THIS ASSUMES YOU ALREADY SET UP THE STEAMWORKS EXTENSION AND HAVE IT RUNNING!
# To create a lobby
### First, start up the server software
### Then, call the net_steamhost_init(...) function
```gml
// For example
net_steamhost_init({
  ip: "127.0.0.1",
  port: 25565
})
```
### If you also want to connect, just call net_connect and pass in the server_endpoint too
# To join a lobby
### Simply call net_steamclient_init(...), refer to documentation on how to do that
## Code documentation
```gml
/*
  Creates a lobby and connects the server to the lobby
*/
function net_steamhost_init(server_endpoint: 
{
  ip: string,
  port: real
}, [lobby_type = steam_lobby_type_public]) -> N/A
```
```gml
/*
  Connects to a lobby and creates sockets to let the NetGM2 client to connect to the lobby
*/
function net_steamclient_init(lobby_id: real, tunnel_port: real) -> N/A
```