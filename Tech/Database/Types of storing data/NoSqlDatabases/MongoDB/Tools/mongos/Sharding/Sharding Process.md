the [[Sharding]] of a [[MongoDB]].

1. Client sends request to [[mongos]].
2. [[mongos]] routes each request to the appropriate shard based on what the [[Config Servers]] responds.
3. the [[Config Servers]] returns where [[Routers]] can redirect the request to.
 (if you have 3 shards or less, you can use a [[Config Shard]] in this case).


visual map: [[mongos.excalidraw]]