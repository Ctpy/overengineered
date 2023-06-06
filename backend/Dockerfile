FROM gradle:latest AS build

COPY --chown=gradle:gradle . /home/gradle/src

WORKDIR /home/gradle/src

RUN ./gradlew build --no-daemon

FROM openjdk:21-ea-18-slim-buster

WORKDIR /backend

ARG JAR_FILE=build/libs/*.jar

COPY ${JAR_FILE} backend.jar

CMD ["java", "-jar", "backend.jar"]