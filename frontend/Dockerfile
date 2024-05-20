# Use the official Vue image as the base image
FROM node:14-alpine

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY ./frontend/app/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the project files
COPY ./frontend/app .

# Build the Vue app
RUN npm run build

# Expose the port the app runs on
EXPOSE 8080

# Serve the app
CMD ["npm", "run", "serve"]
