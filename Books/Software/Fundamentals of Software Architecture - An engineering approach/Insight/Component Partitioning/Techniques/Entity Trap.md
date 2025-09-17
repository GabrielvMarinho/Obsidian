Imagine an auction system.
An architect might structure the architecture in the following components (entities):

Auction Manager
  ├── Create auctions
  ├── Browse auctions
  └── Schedule auctions

Item Manager
  ├── Create item
  ├── Display item
  └── Upload item

Bid Manager
  ├── Place bids
  ├── Display bids
  └── Track bids

The architect has fallen for the entity trap.
This isnt architecture, its a component-relational mapping of a framework to a database, if the system only needs a simple database CRUD, then the architect can download a framework to create user interfaces directly from the database. 