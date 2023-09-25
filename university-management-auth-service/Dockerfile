# Use an official Node runtime as a base image
FROM node:16

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy the package.json and yarn.lock
COPY package.json yarn.lock ./

# Install dependencies
RUN yarn install --production=false

# Copy the source code into the container
COPY . .

# Build the TypeScript code
RUN yarn tsc

# Expose the port the app runs on
EXPOSE 3001

# Command to run the application
CMD ["yarn", "start"]
