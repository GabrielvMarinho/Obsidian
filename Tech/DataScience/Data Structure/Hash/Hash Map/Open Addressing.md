a specific way to populate a [[Hash Table]]

Position is not 100% defined by the [[Hash]], it varies on if there is already an element, instead of a collision or rewriting, the value is placed somewhere else

## If collision, where to store

If a collision happens, generally an open addressing structure will just keep on incrementing the key to find an empty spot

## Resizing

if the array runs out of addresses, you have to resize and recalculate all the positions