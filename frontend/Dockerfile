# frontend/Dockerfile

# Use the official Node.js image to build the React app
FROM node:18 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./

# Set NODE_ENV to production (optional for optimized builds)
ENV NODE_ENV=production

# Install dependencies
RUN npm install

# Copy the rest of the application code to /app
COPY . .

# Build the React app
RUN npm run build

# Debug: List the contents of the /app directory
RUN ls -la /app

# Debug: List the contents of the /app/build directory
RUN ls -la /app/build

# Use Nginx to serve the static files
FROM nginx:alpine

# Copy the /app directory from the build stage to the final image
COPY --from=build /app /app

# Copy the build output to the Nginx HTML directory
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80 for the frontend
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
