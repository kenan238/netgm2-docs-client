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
  The NetGM2 api key for your app
*/
#macro net_key "[KEY HERE]"
```