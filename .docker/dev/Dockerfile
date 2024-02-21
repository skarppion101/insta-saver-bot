ARG NODE_VERSION=20.10

FROM node:${NODE_VERSION}-alpine

# Create and define the node_modules's cache directory.
WORKDIR /cache

# install app dependencies
COPY package.json .
COPY package-lock.json .

# Use production node environment by default.
ENV NODE_ENV development

# Install git
RUN apk add git

# Install deps.
RUN npm install -g nodemon
RUN npm install

WORKDIR /app

ENV PATH /app/node_modules/.bin:$PATH

# Copy the rest of the source files into the image.
COPY . .
