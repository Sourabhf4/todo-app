# Multi-Stage Dockerfile – Node.js

## Dockerfile

```dockerfile
# Stage 1: Build
FROM node:16-alpine AS build

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .


# Stage 2: Run
FROM node:16-alpine

WORKDIR /usr/src/app

COPY --from=build /usr/src/app .

EXPOSE 3000

CMD ["npm", "start"]
