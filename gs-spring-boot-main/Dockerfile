# Start your image with a java base image
FROM openjdk:17

# The /app directory should act as the main application directory
WORKDIR /app

# Copy the app package and package-lock.json file
COPY pom.xml ./

# Copy local directories to the current local directory of our docker image (/app)
COPY ./src ./src

# Install node packages, install serve, build the app, and remove dependencies at the end
RUN mvn clean install

EXPOSE 8080

# Start the app using serve command
CMD [ "serve", "-s", "build" ]