# Use a base image with the appropriate JDK version (Java 21 in your case)
FROM eclipse-temurin:21-jdk as build

# Set the working directory inside the container
WORKDIR /app

# Copy the Maven build files and source code
COPY . . 

# Build the application using Maven
RUN mvnw clean package -DskipTests

# Use a smaller base image for running the app
FROM eclipse-temurin:21-jre

# Set the working directory for the runtime container
WORKDIR /app

# Copy the built application JAR file from the build stage
COPY --from=build /app/target/authentification-manager-ms-0.0.1-SNAPSHOT.jar app.jar

# Expose the application's default port (e.g., 8080)
EXPOSE 8080

# Run the Spring Boot application
ENTRYPOINT ["java", "-jar", "app.jar"]