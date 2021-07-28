
# Base Image
FROM node:alpine as builder

# Change workdir to '/app'
WORKDIR 'usr/app'

# Copy package.json into 
# the container
COPY package.json .

# Install dependencies
RUN npm install

# Copy the rest of the 
# files into the container
COPY . .

# Build the production files
RUN npm run build

## RUN PHASE
# Base image
FROM node:alphine as prod

WORKDIR "/app"

# Cpoy over the production files
# to the nginx webroot
COPY --from=builder /user/app/ .