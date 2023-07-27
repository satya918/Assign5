# Use a base image suitable for your application. For example, if it's a Node.js app:
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json files to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY . .

# Specify the command to start your application
CMD ["npm", "start"]

