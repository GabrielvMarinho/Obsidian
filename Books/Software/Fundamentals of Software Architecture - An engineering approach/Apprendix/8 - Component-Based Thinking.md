1. We define the term component as a building block of an application—something
the application does. A component usually consist of a group of classes or source
files. How are components typically manifested within an application or service?
- as subsystems or layers

2. What is the difference between technical partitioning and domain partitioning?
Provide an example of each.
- focusing the partitioning in technical structure: layered architecture, partition in bussiness layer, persistence layer, view layer
- focusing the partitioning in bussiness related needs: micro services, a single service for each bussiness domain feature/workflow

3. What is the advantage of domain partitioning?
- It is specific to the necessities of the domain

4. Under what circumstances would technical partitioning be a better choice over
domain partitioning?
- when the lack of experience and need for fast/standardized development exists

5. What is the entity trap? Why is it not a good approach for component
identification?
- the entity trap is basically seeing the architecture as entities that makes actions and offer no insights, this often builds a generic architecture and provides no values other than what a crud would have

6. When might you choose the workflow approach over the Actor/Actions
approach when identifying core components?
- when you have a clear or numerous separation of roles in a system
- when you need upfront design
