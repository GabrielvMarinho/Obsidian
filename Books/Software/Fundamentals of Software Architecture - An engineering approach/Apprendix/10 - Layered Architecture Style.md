1. What is the difference between an open layer and a closed layer?
- a closed layer is a layer that needs to pass another in order to create a flow in an api call, open layers can be passed freely

2. Describe the layers of isolation concept and what the benefits are of this concept.
- isolating layers into specific tasks, like view, bussinness and persistence, this gives a clear vision of what each part of the system does, this concept implies that a change in a given layer shouldnt affect other.

3. What is the architecture sinkhole anti-pattern?
- when you pass a layer just for the sake of passing it and it doesnt add any value to the response of a request

4. What are some of the main architecture characteristics that would drive you to
use a layered architecture?
- simplicity
- cheapness

5. Why isn’t testability well supported in the layered architecture style?
- because its single quanted and generally the layers are tightly coupled

6. Why isn’t agility well supported in the layered architecture style?
- because generally you become coupled to a specific technology for the layers of the architecture