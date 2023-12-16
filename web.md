### [< BACK](start.md)

# Web API & analytics
## Synopsis:
NetGM2 analytics & api functions.
## Code documentation
```gml
/*
  Get all the active servers on the netgm2 app
  NOTE: _callback takes the following arguments: _callback(_succeded: bool, servers: List<server>)
*/
function net_web_get_servers(_callback) -> N/A
```
```gml
/*
  * Inside of Net script *
  The NetGM2 api key for your app
*/
#macro net_key "[KEY HERE]"
```
```gml
/*
  Gets the latest version ID of NetGM2 from the servers
  NOTE: _callback takes the following arguments: _callback(_succeded: bool, servers: VersionStruct)

  VersionStruct is a struct with a single key, "version", which contains the latest version.
*/

function net_web_get_version(_callback) -> N/A
```