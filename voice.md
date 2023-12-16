### [< BACK](start.md)

# Voice chat
└── Inherits from `Stream`
## Synopsis:
Using streams to transfer audio, there's an additional voice chat feature
## Prelude
### Enabling voice chat means that Streams with id 0xff (255) are occupied and cannot be used
## Code documentation
```gml
/*
  Call this after `net_connect`
*/
function net_voice_init() -> N/A
```
```gml
/*
  Pass in the recorder number (call this BEFORE init)
*/
function net_voice_set_recorder(_recorder) -> N/A
```