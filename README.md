
# Technologies
- Spring Boot 2.7.0
- Angular 14
- MySql 8.0

# Run locally
## Backend

    Requirement - JDK 17 and maven 3.8.6 should be installed
    ```
    cd backend
    mvn clean install
    java -jar target/twitter-clone-0.0.1-SNAPSHOT.jar
    ```

## frontend
    Requirements - Latest node and npm install. Angular cli 14
    ```
    > cd frontend
    > npm install
    > ng serve
    ```
    Open in browser http://localhots:4200

# Docker   
## Frontend

    ```
    > cd frontend
    > ng build --configuration production --aot
    > docker build -t frontend .
    > docker run -p 8080:80 --name webapp -d frontend
    ```
    Access web application using url: http://localhost:8080/

## Backend
    ```
    > cd backend
    
    ```
    Access web application using url: 


## Swager url
http://localhost:8080/swagger-ui.html