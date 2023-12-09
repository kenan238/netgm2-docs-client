# Administration
## Synopsis:
Chat system, self explanatory
## Code documentation
```gml
/*
  Sends a message (supports commands)
*/
function net_chat_send(_msg) -> N/A
```

```gml
/*
  Creates a command and attaches a callback to it
*/
function net_chat_add_cmd(_cmd, _callback) -> N/A
```

```gml
/*
  Gets the chat contents
*/
function net_chat_get() -> Struct {
  content: string,
  cid: UserId,
}
```