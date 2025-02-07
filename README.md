﻿# DevOps-Lab-Final
## Frontend: React User Interface
### Dockerfile (Frontend)
```Dockerfile
# Use the official Node.js image as the base image
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json (if available)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose port 5173 (default Vite port for dev server)
EXPOSE 5173

# Start the development server (this is for development purposes)
CMD ["npm", "run", "dev"] 
```
## Commands for Frontend
1. Build the Docker Image

```
docker build -t react-user-interface .
```
2. Run Locally
```
docker run -it -p 5173:5173 react-user-interface
Visit http://localhost:5173.
```
3. Tag the image
```
docker tag react-user-interface abdulmoiz833/react-user-interface:latest
```
4. Push to docker hub
```
docker login
docker push abdulmoiz833/react-user-interface:latest
```
