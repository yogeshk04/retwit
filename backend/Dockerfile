# Build Stage
FROM maven:3.8.5-openjdk-17-slim AS build
COPY pom.xml /app/
COPY src /app/src
RUN mvn -DskipTests -f /app/pom.xml clean package

# Run Stage
FROM openjdk:17
COPY --from=build /app/target/retwit*.jar /app/app.jar
ENTRYPOINT ["java", "-XX:+UnlockExperimentalVMOptions", "-XX:+UseCGroupMemoryLimitForHeap","-Djava.security.egd=file:/dev/./urandom","-jar","/app/app.jar"]
