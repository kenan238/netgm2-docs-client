# Administration
## Synopsis:
An event system where you can listen to specific events and run code between actions, it is not asynchronous
## Code documentation
```gml
/*
  Attaches a callback to the specified event (you can attach multiple callbacks to the same event)
*/
function net_add_event_listener(_event_name, _callback) -> N/A
```