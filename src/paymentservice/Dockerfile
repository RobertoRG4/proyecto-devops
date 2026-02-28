FROM node:20.20.0-alpine

RUN apk add --no-cache python3 make g++

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install --omit=dev

COPY . .

EXPOSE 50051

ENTRYPOINT ["node","index.js"]