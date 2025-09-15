Can be technically based or domain based ->

Lets imagine two monoliths:
1. Technical separation: Presentation layer, bussiness layer, persistance layer
2. Domain separation: UpdateCatalog, ShipToClient, ClientLogon

an implementation of technical separation is MVC model.
in this case, each domain separation can utilize a different persistance library for example. 