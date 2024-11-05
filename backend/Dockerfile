# Dockerfile

# Use the official Node.js LTS image
FROM node:18

# Set the working directory in the container
WORKDIR /app

# Initialize a basic package.json if it doesn’t exist
RUN npm init -y

# Install essential npm packages
RUN npm install express pg dotenv nodemon --save

# Copy the rest of the application code into the container
COPY . .

# Expose the application port
EXPOSE 3000

# Start the application
CMD ["node", "index.js"]
