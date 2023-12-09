# Administration
## Synopsis:
Streams are continuous _streams_ of bytes that can transfer any datatype, clients can subscribe to any player's stream and receive all the bytes being transferred 
## Code documentation
```gml
/*
  Registers a stream (stream only gets created when server receives the request)
*/
function net_stream_register(_id) -> N/A
```
```gml
/*
  Deletes a stream
*/
function net_stream_destroy(_id) -> N/A
```
```gml
/*
  Writes data to a stream
*/
function net_stream_data(_id, _buffer, _reliable) -> N/A
```
```gml
/*
  Gets a stream's index in the obj_net.streams array

  It is preferred you use `net_stream_get` instead

  NOTE: _ownerid is the ID of the player that owns the stream, and _id is the id of the stream itself
*/
function net_stream_get_index(_ownerid, _id) -> Real
```
```
/*
  Gets a stream's index in the obj_net.streams array

  It is preferred you use `net_stream_get` instead

  NOTE: _ownerid is the ID of the player that owns the stream, and _id is the id of the stream itself
*/
function net_stream_get(_ownerid, _id) -> NetStream
```
```gml
/*
  NetStream constructor's functions
*/
function NetStream() constructor {
  function SetListener(_listener: Callback) /* This listener will be called whenever there's a new chunk of data */
  
  function ResetListener() /* Will reset the listener and acts as an un-subscribe */
}
```