# Stage 1: Build Angular frontend
FROM node:14.17.0-alpine AS frontend-builder

WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the entire Angular project
COPY . .

# Build the Angular app
RUN npm run build

# Expose the desired port (8081) for the ng serve command
EXPOSE 8081

# Run the Angular app using the ng serve command
<<<<<<< HEAD
CMD ["npm", "run", "start", "--", "--host", "0.0.0.0", "--port", "8081"]
=======
CMD ["npm", "run", "start", "--", "--host", "0.0.0.0", "--port", "8081"]
>>>>>>> origin/anas-prog
