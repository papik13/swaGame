# Use Node.js 18 on Debian Bullseye as the base image
FROM mcr.microsoft.com/devcontainers/javascript-node:1-18-bullseye

# Set the working directory in the container
WORKDIR Frontend/app

# Copy package.json and package-lock.json (if available)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of your application's code
COPY . .

# Build your Nuxt.js application
RUN npm run build

# Expose port 3000 for the server
# Nuxt.js typically runs on port 3000 by default, but adjust if your app uses a different port
EXPOSE 3000

# Command to run your app
CMD ["npm", "run", "dev"]
