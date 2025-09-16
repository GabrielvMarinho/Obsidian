Can be technically based or domain based ->

Lets imagine two monoliths:
1. Technical separation: Presentation layer, bussiness layer, persistance layer
2. Domain separation: UpdateCatalog, ShipToClient, ClientLogon

an implementation of technical separation is MVC model.
in this case, each domain separation can utilize a different persistance library for example. 

## Technical partitioning
PROS.
clearly separates customization code
aligns better with layered architecture pattern
CONS.
Higher degree of global coupling

## Domain partitioning
PROS.
flow matches the problem domain
easier to migrate or adapt to a distributed architecture
more focus on bussiness functions instead of implementation detail

CONS.
Customization code appears in multiple places
