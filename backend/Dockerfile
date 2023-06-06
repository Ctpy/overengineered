FROM gradle:jdk18-alpine as build

WORKDIR /backend
COPY build.gradle .
COPY settings.gradle .
COPY . .
RUN gradle build --no-daemon

FROM openjdk:21-ea-18-slim-buster

WORKDIR /backend

COPY --from=build /backend/build/libs/*.jar backend.jar

CMD ["java", "-jar", "backend.jar"]