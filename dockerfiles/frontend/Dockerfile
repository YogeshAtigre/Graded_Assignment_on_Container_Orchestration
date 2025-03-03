# Stage 1: Build Stage
FROM node:18-slim AS buildstage
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install --legacy-peer-deps

# Copy the rest of the app code
COPY . .

# Build the application (for React frontend)
RUN npm run build

# Stage 2: Final Image
FROM node:18-slim AS finalstage
WORKDIR /usr/src/app

# Copy built files from the build stage
COPY --from=buildstage /usr/src/app . 

EXPOSE 3000
CMD ["npm", "start"]
