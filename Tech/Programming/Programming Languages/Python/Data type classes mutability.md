Table with the mutability of the data types

| Immutable | Mutable                |
| --------- | ---------------------- |
| int       | list                   |
| float     | dict                   |
| complex   | set                    |
| bool      | bytearray              |
| str       | collections.deque      |
| tuple     | array.array            |
| frozenset | custom class instances |
| bytes     |                        |
| NoneType  |                        |
| range     |                        |

Generally, data types that are immutable will have a new memory address when changed. A string "value" assigned to x and y, will end up with x and y pointing to the same address (that doesnt apply to all scenarios).

On the other hand, mutable types will not change the address, and even if created with the same content, will point to different addresses.