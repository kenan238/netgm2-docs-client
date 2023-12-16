### [< BACK](start.md)

# Debug
## Synopsis:
Debugging functions for NetGM2 and redirecting log output for various log types.
## Code documentation
```gml
/*
  Set a callback that will be called whenever something is logged with the
    message as the parameter
*/
function net_debug_set_logger(_callback) -> N/A
```
```gml
/*
  Set a callback that will be called whenever something _verbose_ is logged with the
    message as the parameter
*/
function net_debug_set_verbose_logger(_callback) -> N/A
```
```gml
/*
  This is only intended for me, when I want to debug
  NetGM2 itself, this function won't do anything
  on release versions, anyway.
*/
function net_debug_set_dev_logger(_callback) -> N/A
```