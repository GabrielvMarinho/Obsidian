used to create [[Docker Image]]

## **1 - Base image**
FROM "[[RTE]]"

the minimal os given by docker hub
## **2 - Set working directory** 

WORKDIR "/app"

basically tells docker file system where to place the application 
## **3 - Copy the application code**
COPY ". ."

gets the application code (generally already built)
## 4 - **Set the command to run the application**
CMD "command to run the app"
