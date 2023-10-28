# Use a base image with a JRE
FROM mcr.microsoft.com/openjdk/jdk:17-mariner

# Set the working directory
WORKDIR /app

# Copy the JAR file into the container
COPY target/springboot-crud-h2-1.0.jar app.jar

# Expose the port your application is running on
EXPOSE 80

# Command to run the application
CMD ["java", "-jar", "app.jar"]
