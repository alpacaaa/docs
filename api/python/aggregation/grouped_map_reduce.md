---
layout: api-command 
language: Python
permalink: api/python/grouped_map_reduce/
command: grouped_map_reduce
related_commands:
    map: map/
    concat_map: concat_map/
    group_by: group_by/
---

# Command syntax #

{% apibody %}
sequence.grouped_map_reduce(grouping, mapping, reduction, base)
    &rarr; value
{% endapibody %}

# Description #

Partition the sequence into groups based on the `grouping` function. The elements of each
group are then mapped using the `mapping` function and reduced using the `reduction`
function.

`grouped_map_reduce` is a generalized form of group by.

__Example:__ It's only fair that heroes be compared against their weight class.

```py
r.table('marvel').grouped_map_reduce(
    lambda hero: hero['weightClass'],  # grouping
    lambda hero: hero.pluck('name', 'strength'),  # mapping
    lambda acc, hero: r.branch(acc['strength'] < hero['strength'], hero, acc),
    {'name':'none', 'strength':0}  # base
).run(conn)
```


