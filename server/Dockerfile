FROM adoptopenjdk:14-jdk-hotspot as builder

WORKDIR /app

COPY . .

RUN ./gradlew build

FROM adoptopenjdk:14-jre-hotspot

WORKDIR /app

COPY --from=builder app/build/libs/challenge-0.0.1-SNAPSHOT.jar app.jar

EXPOSE 8080

CMD ["java", "-jar", "app.jar"]