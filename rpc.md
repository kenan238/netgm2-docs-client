### [< BACK](start.md)

# RPC (Remote Procedural Calls)
## Synopsis:
Functions that can be called from the opposite side, for example

**Server** Rpc Functions can be called from **Any Client**

**Client** Rpc Functions can be called from **the server**
## Code documentation
```gml
/*
  Register an rpc function that can be called from the server
*/
function net_rpc_register(_name, _callback) -> N/A
```
```gml
/*
  Call a server rpc function
*/
function net_rpc_call(_name, _reliable) -> N/A
```