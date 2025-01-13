#stage 1
# Use the official Node.js image as the base image
FROM node:20 AS builder

# Set the working directory inside the container
WORKDIR /app

# Copy the current directory contents to the working directory inside the container
COPY . /app

# Install the dependencies
RUN npm install

# Build the application (optional for production builds, use if needed)
RUN npm run build

# Expose the port on which the app will run (React's default is often 3000, or use 5173 for Vite)
EXPOSE 5173

# Start the application using `npm run dev` or another command for your production app
CMD ["npm", "run", "dev"]
