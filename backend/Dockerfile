# Build Stage
FROM maven:3.8.5-openjdk-17-slim AS build
WORKDIR /app
COPY pom.xml .
COPY src /app/src
RUN mvn -DskipTests clean package

# Run Stage
FROM openjdk:17.0-jdk-slim
WORKDIR /app
COPY --from=build /app/target/retwit*.jar /app/app.jar
ENTRYPOINT ["java", "-Xms512m", "-Xmx1024m", "-jar", "/app/app.jar"]
