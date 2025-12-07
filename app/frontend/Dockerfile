# -------------------------
# FRONTEND DOCKERFILE (Angular)
# Path: app/frontend/Dockerfile
# -------------------------

# Stage 1: Build Angular App
FROM node:20-alpine as build

WORKDIR /app

COPY package.json package-lock.json* ./
RUN npm install

COPY . .

# Build Angular production output
RUN npm run build --prod

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Replace <project-name> with your actual Angular dist folder
COPY --from=build /app/dist/todo-app-ui /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
