# Use an official Node.js image as the base image
FROM node:18-alpine

# Set working directory
RUN mkdir -p /client
WORKDIR /client

# Copy package.json and install dependencies
COPY package*.json /client/
RUN npm install --production

# Copy the rest of the application
COPY . /client/
# CMD ["npm", "run", "start"]
RUN npm run build

RUN npm install -g serve
CMD ["serve", "-s", "build", "-l", "3000"]
EXPOSE 3000

# FROM nginx:alpine
# COPY --from=0 /client/build /usr/share/nginx/html

# EXPOSE 3000

# CMD ["nginx", "-g", "daemon off;"]
