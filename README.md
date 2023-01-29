bash

# Use an existing Docker image as the base image
FROM node:14

# Create a directory for the application
WORKDIR /app

# Copy the package.json file to the image
COPY package.json .

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the image
COPY . .

# Build the React application
RUN npm run build

# Specify the command to run the application when the container is started
CMD ["npm", "start"]

In diesem Dockerfile wird zunächst ein vorhandenes Docker-Image als Basis verwendet. Danach wird ein Verzeichnis für die Anwendung erstellt und die Abhängigkeiten installiert. Schließlich wird die Anwendung gebaut und konfiguriert, um beim Starten des Containers gestartet zu werden.
