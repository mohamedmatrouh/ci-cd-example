# Set the base image to use
FROM maven:3.8.4-openjdk-8-slim

# Set the working directory inside the container
RUN mkdir /app
WORKDIR /app

# Copy the POM file to the container
COPY ./pom.xml /app/pom.xml


# Download the project dependencies
RUN mvn dependency:go-offline -B

# Copy the application source code to the container
COPY ./src /app/src

# Build the application
RUN mvn package

EXPOSE 8080
# Set the entrypoint command to run the application
WORKDIR /app/target/
RUN chmod 777 spring-boot-jpa-h2-0.0.1-SNAPSHOT.jar
CMD ["java", "-jar", "spring-boot-jpa-h2-0.0.1-SNAPSHOT.jar"]
