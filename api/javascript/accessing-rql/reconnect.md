---
layout: api-command 
language: JavaScript
permalink: api/javascript/reconnect/
command: reconnect
io:
    -   - connection
        - undefined
related_commands:
    connect: connect/
    use: use/
    close: close/
---

# Command syntax #

{% apibody %}
conn.reconnect()
{% endapibody %}

# Description #

Close and attempt to reopen a connection. Has the effect of canceling any outstanding
request while keeping the connection open.

__Example:__ Cancel outstanding requests/queries that are no longer needed.

```js
conn.reconnect(function(errror, connection) { ... })
```
