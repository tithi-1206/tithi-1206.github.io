# A Step-by-Step Guide to Uploading Container Images to Dockerhub

Following is the tutorial on uploading container images to Dockerhub! In this guide, we'll walk you through the process of sharing your Docker images with others or deploying them to production environments using Dockerhub's cloud-based registry service.

## Prerequisites

Before you begin, make sure you have the following prerequisites:

- Docker installed on your local machine
- A Dockerhub account (you can sign up for free at [Dockerhub](https://hub.docker.com/))

## Step 1: Build Your Docker Image

First, you need to build your Docker image locally on your development machine. Start by creating a Dockerfile in your project directory with the necessary instructions to build your image. Here's a basic example of a Dockerfile for a Node.js application:

```dockerfile
# Use the official Node.js image as a base
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Expose port 3000
EXPOSE 3000

# Define the command to run the application
CMD ["npm", "start"]
```

![Alt text](image1.png)


## Step 2: Tag Your Docker Image

Once you have built your Docker image, you need to tag it with your Dockerhub username and the desired repository name. Use the following command to tag your image:

```
docker tag <image-id> <your-dockerhub-username>/<repository-name>:<tag>
```

![Alt text](image2.png)


Replace <image-id> with the ID of your Docker image (you can find this by running docker images), <your-dockerhub-username> with your Dockerhub username, <repository-name> with the name of your repository on Dockerhub, and <tag> with a version tag for your image (e.g., latest).

## Step 3: Login to Dockerhub

Before you can push your Docker image to Dockerhub, you need to login to your Dockerhub account using the following command:

```
docker login
```

![Alt text](image3.png)


Enter your Dockerhub username and password when prompted.

## Step 4: Push Your Docker Image to Dockerhub

Finally, you can push your Docker image to Dockerhub using the following command:

```
docker push <your-dockerhub-username>/<repository-name>:<tag>
```

![Alt text](image4.png)


Replace <your-dockerhub-username>, <repository-name>, and <tag> with the corresponding values.

## Conclusion

You have successfully uploaded your Docker image to Dockerhub. You can now share it with others or deploy it to production environments using Dockerhub's cloud-based registry service.
