# Use an official Node runtime as a base image
FROM node:16

# Set environment variables (if needed)
# ENV DATABASE_URL=your_database_url_here

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy the package.json and yarn.lock
COPY package.json yarn.lock ./

# Install Prisma CLI globally
RUN npm install -g prisma

# Install dependencies
RUN yarn install --production=false

# Copy the source code into the container
COPY . .

# Generate Prisma Client
RUN npx prisma generate

# Run migrations (be cautious when doing this)
RUN npx prisma migrate deploy

# Build the TypeScript code
RUN yarn build

# Expose the port the app runs on
EXPOSE 3002

# Command to run the application
CMD ["yarn", "start"]
