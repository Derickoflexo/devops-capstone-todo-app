# -------------------------
# BACKEND DOCKERFILE
# Path: app/backend/Dockerfile
# -------------------------

FROM node:20-alpine

# Create app directory
WORKDIR /app

# Copy package files
COPY package.json package-lock.json* ./

# Install dependencies
RUN npm install --production

# Copy all backend source code
COPY . .

# Expose backend port
EXPOSE 4000

# Start the backend server
CMD ["npm", "start"]

