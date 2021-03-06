---
layout: api-command 
language: JavaScript
permalink: api/javascript/add_listener/
command: addListener 
py: false
rb: false
io:
    -   - connection
        - undefined
related_commands:
    connect: connect/
    reconnect: reconnect/
    close: close/
---

# Command syntax #

{% apibody %}
connection.addListener(event, listener)
{% endapibody %}

# Description #

The connection object also supports the event emitter interface so you can listen for
changes in connection state.

__Example:__ Monitor connection state with events 'connect', 'close', and 'error'.


```js
r.connect({}, function(err, conn) {
    if (err) throw err;

    conn.addListener('error', function(e) {
        processNetworkError(e);
    });

    conn.addListener('close', function() {
        cleanup();
    });

    runQueries(conn);
});

```

__Example:__ As in Node, 'on' is a synonym for 'addListener'.

```js
conn.on('close', function() {
    cleanup();
});
conn.close();
```

