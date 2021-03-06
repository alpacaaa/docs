---
layout: api-command 
language: JavaScript
permalink: api/javascript/coerce_to/
command: coerceTo
io:
    -   - sequence
        - array
    -   - value
        - string
    -   - array
        - object
    -   - object
        - array
---

# Command syntax #

{% apibody %}
sequence.coerceTo(typeName) &rarr; array
value.coerceTo(typeName) &rarr; string
array.coerceTo(typeName) &rarr; object
object.coerceTo(typeName) &rarr; array
{% endapibody %}

# Description #

Converts a value of one type into another. 

You can convert: a selection, sequence, or object into an ARRAY, an array of pairs into an OBJECT, and any DATUM into a STRING.

__Example:__ Convert a table to an array.

```js
r.table('marvel').coerceTo('array').run(conn, callback)
```


__Example:__ Convert an array of pairs into an object.


```js
r.expr([['name', 'Ironman'], ['victories', 2000]]).coerceTo('object').run(conn, callback)
```

__Example:__ Convert a number to a string.

```js
r.expr(1).coerceTo('string').run(conn, callback)
```

