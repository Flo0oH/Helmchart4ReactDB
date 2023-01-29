Dockerfile for a Simple React Hello World App

This repository provides a Dockerfile for a simple React app that displays a "Hello World" message.
Prerequisites

    Docker installed on your local machine

Building the Image

    Clone this repository to your local machine and navigate to the directory. Run the following command to build the Docker image:


    docker build -t my-react-app .

Running the Container

Once the image has been built, you can run the container with the following command:

css

    docker run -p 3000:3000 my-react-app

The app will be accessible at http://localhost:3000 in your web browser.
Dockerfile Configuration


bash

# Use an official Node.js runtime as the base image


And the package.json file should contain the following:


The React component displaying the "Hello World" message should be stored in a file named index.js.
