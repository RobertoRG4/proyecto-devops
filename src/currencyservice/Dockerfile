FROM node:20.20.0-alpine

RUN apk add --no-cache \
    python3 \
    make \
    g++

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install --only=production

COPY . .

EXPOSE 7000
ENTRYPOINT [ "node", "server.js" ]