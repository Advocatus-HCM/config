# Use an official OpenJDK runtime as a parent image
FROM openjdk:21-jdk-slim

WORKDIR /app
# Set the working directory in the container
ARG JAR_FILE=target/*.jar
# Copy the JAR file from your microservice's target directory to the container
# Adjust the relative path to match your directory structure
COPY ./target/authentification-manager-ms-0.0.1-SNAPSHOT.jar app.jar

# Expose the port that the application will run on
EXPOSE 8080

# Run the JAR file
ENTRYPOINT ["java", "-jar", "app.jar"]
