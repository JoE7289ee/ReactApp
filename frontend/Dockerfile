# frontend/Dockerfile

# Use the official Node.js image
FROM node:18

# Set the working directory
WORKDIR /app

# Copy package.json to the container
COPY package.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose port 3000 for the React development server
EXPOSE 3000

# Run the React development server
CMD ["npm", "start"]
