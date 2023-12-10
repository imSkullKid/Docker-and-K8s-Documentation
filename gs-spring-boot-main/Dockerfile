# Start your image with a java base image
FROM eclipse-temurin:17-jdk-alpine

# Creates the /app directory should act as the main application directory
WORKDIR /app

# Copy the pom and place it in the base directory of the image
COPY pom.xml ./

# Create an ARG called JAR_FILE, which we can call on during the new image creation
ARG JAR_FILE

# Copies the parameter provided during image creation and copies it titled app.jar
COPY ${JAR_FILE} app.jar

#Expose the port
EXPOSE 8080

# Start the app using the java -jar command
ENTRYPOINT ["java","-jar","app.jar"]
# The command to create the image is `docker build --build-arg JAR_FILE=target/*.jar -t myimage .`
# To run the image as a container it is `docker run -p 8080:8080 myimage`