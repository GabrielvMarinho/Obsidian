A continous integration continuous deploying pipeline that is used to test an application, its usually done by a clean/empty [[Operating System]] that executes some logic to test the software

### How it works

You will create something like a [[JUnit]] setup to test your code, you would somehow then tell the pipeline to run this file on changes/on commits

### How does it communicate with the pipeline

Generally its through [[Yaml]] files that specify how the tests will be run (which os), installing dependencies and what files needs to be run to test