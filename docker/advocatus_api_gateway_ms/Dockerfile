# Use the official Node.js image as the base image
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package.json package-lock.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Ensure that the node_modules/.bin directory is executable
RUN chmod -R 755 ./node_modules/.bin

# Expose the port the app runs on
EXPOSE 4000

# Command to run the application
CMD ["npm", "start"]