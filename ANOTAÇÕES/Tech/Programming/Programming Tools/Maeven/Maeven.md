Compilation automation Tool used primarily in [[Java]]

It helps to manage their project and the thing they need to build their programs

## Commands

./mvnw clean - cleans the target/ directory (which stores the compiled files and build outputs)
./mvnw compile - compiles the source code of the project                             
./mvnw test - runs unit tests in your project 
./mvnw package - creates a .jar file and stores in the target directory (used for deploying to production)
./mvnw verify - runs all lifecylcle phases 
./mvnw spring-boot:run - runs [[Spring]] application through maeven [[Plugin]]