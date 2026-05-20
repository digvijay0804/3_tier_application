FROM maven:3.8.4-openjdk-11 AS build

WORKDIR /app

COPY . .

RUN mvn clean package

FROM adoptopenjdk/openjdk11:alpine-jre

COPY --from=build /app/target/student-service-docker.jar app.jar

ENTRYPOINT ["java","-jar","/app.jar"]
