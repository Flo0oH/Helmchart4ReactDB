Dockerfile for a Simple React Hello World App

This repository provides a Dockerfile for a simple React app that displays a "Hello World" message.
Prerequisites

    Docker installed on your local machine

Building the Image

Clone this repository to your local machine and navigate to the directory. Run the following command to build the Docker image:

perl

docker build -t my-react-app .

Running the Container

Once the image has been built, you can run the container with the following command:

css

docker run -p 3000:3000 my-react-app

The app will be accessible at http://localhost:3000 in your web browser.
Dockerfile Configuration

Here's the content of the Dockerfile:

bash

# Use an official Node.js runtime as the base image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and package-lock.json files to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app's source code to the container
COPY . .

# Build the app for production
RUN npm run build

# Expose port 3000 for incoming traffic
EXPOSE 3000

# Specify the command to run the app
CMD ["npm", "start"]

And the package.json file should contain the following:

json

{
  "name": "my-react-app",
  "version": "1.0.0",
  "private": true,
  "dependencies": {
    "react": "^17.0.1",
    "react-dom": "^17.0.1"
  },
  "scripts": {
    "start": "node server.js",
    "build": "npx react-scripts build"
  }
}

The React component displaying the "Hello World" message should be stored in a file named index.js.
