1. Can pipes be bidirectional in a pipeline architecture?
- typically they aren't

2. Name the four types of filters and their purpose.
- Producer: starting point
- Tranformer: does something with the input
- Tester: accepts input
- Consumer: ending point
 
3. Can a filter send data out through multiple pipes?
- no, its generally divided into more filters if the action is separated

4. Is the pipeline architecture style technically partitioned or domain partitioned?
- Technical

5. In what way does the pipeline architecture support modularity?
- by creating a lot of different filters and pipes

6. Provide two examples of the pipeline architecture style.
- excel power query -> a system that goes through a lot of filters and like the pipeline architecture, follows a set of steps and generate an output from an input
- general ETL tools