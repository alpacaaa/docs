---
layout: api-command 
permalink: api/javascript/day_of_week/
command: dayOfWeek
---
{% apibody %}
time.day_of_week() → number
{% endapibody %}

Return the day of week of a time object as a number between 1 and 7 (following ISO 8601 standard). For your convenience, the terms r.monday, r.tuesday etc. are defined and map to the appropriate integer.

__Example:__ Return today's day of week.

```js
r.now().dayOfWeek().run(conn, callback)
```

__Example:__ Retrieve all the users who were born on a Tuesday.

```js
r.table("users").filter(
    r.row("birthdate").dayOfWeek().eq(r.tuesday)
)
```
