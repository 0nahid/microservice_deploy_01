# Use Node.js image
FROM node:16

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./
RUN npm install

# Copy environment variables
COPY .env .env

# Bundle app source
COPY . .

# Generate Prisma client
RUN npx prisma generate

# Expose the port the app runs on
EXPOSE 3002

# Command to run the application
CMD ["npm", "start"]
