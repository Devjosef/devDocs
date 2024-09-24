# Docker

## Introduction
Docker is a platform for developing, shipping, and running applications in containers. It allows you to package an application with all its dependencies into a standardized unit for software development.

## Basic Syntax
```dockerfile
# Use an official Node runtime as a parent image
FROM node:14

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the port the app runs on
EXPOSE 8080

# Run the application
CMD ["node", "app.js"]
````


## Common Use Cases
- Containerizing applications for consistent environments
- Simplifying deployment processes
- Isolating dependencies
- Scaling applications

## Advanced Features
- **Multi-stage Builds**: Optimize Docker images by using multiple stages.
- **Docker Compose**: Define and run multi-container Docker applications.
- **Networking**: Connect multiple containers.
- **Volumes**: Persist data outside of containers.

## Code Snippets
### Multi-stage Build
```dockerfile
# Stage 1: Build
FROM node:14 as build
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Production
FROM nginx:alpine
COPY --from=build /usr/src/app/build /usr/share/nginx/html
````


### Docker Compose
```yaml
version: '3'
services:
  web:
    image: my-web-app
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
```


## Tips & Best Practices
- **Keep Images Small**: Use multi-stage builds and `.dockerignore` to keep images small.
- **Use Volumes**: Use volumes to persist data and manage state.
- **Security**: Regularly update base images and scan for vulnerabilities.
- **Networking**: Use Docker networks to manage communication between containers.

## External Resources
- [Docker Official Documentation](https://docs.docker.com/)
- [Docker Hub](https://hub.docker.com/)
- [Awesome Docker](https://github.com/veggiemonk/awesome-docker)