# Stage 1: Build stage
FROM node:20 AS builder

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json to install dependencies first
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Build the application (for production, optional for development)
RUN npm run build

# Stage 2: Production stage
FROM node:20 AS production

# Set the working directory inside the container for production
WORKDIR /app

# Copy only the necessary files (built app and node_modules) from the builder stage
COPY --from=builder /app/build /app/build
COPY --from=builder /app/node_modules /app/node_modules

# Expose the port on which the app will run
EXPOSE 5173  # Or 3000 depending on your app

# Start the application (using a production build)
CMD ["npm", "run", "start"]
