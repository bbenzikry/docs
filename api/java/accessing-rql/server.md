---
layout: api-command 
language: Java
permalink: api/java/server/
command: server
---

# Command syntax #

{% apibody %}
conn.server() &rarr; Server
conn.serverAsync() &rarr; CompletableFuture<Server>
{% endapibody %}

# Description #

Return information about the server being used by a connection.

The `server` command returns either two or three fields:

* `id`: the UUID of the server the client is connected to.
* `proxy`: a boolean indicating whether the server is a [RethinkDB proxy node][rp].
* `name`: the server name. If `proxy` is `true`, this field will not be returned.

[rp]: /docs/sharding-and-replication/#running-a-proxy-node

__Example:__ Return server information.

```java
conn.server();
```

```json
{
    "id": "404bef53-4b2c-433f-9184-bc3f7bda4a15",
    "name": "amadeus",
    "proxy": false
}
```
