FROM openjdk:8u342

WORKDIR /app/

COPY ./target/spring-boot-jpa-h2-0.0.1-SNAPSHOT.jar /app/app.jar

RUN chmod 777 /app/app.jar
CMD ["java", "-jar", "/app/app.jar"]
