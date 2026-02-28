FROM node:20-bookworm-slim AS builder

RUN apt-get update && apt-get install -y python3 make g++

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm ci --omit=dev

FROM node:20-bookworm-slim

WORKDIR /usr/src/app
COPY --from=builder /usr/src/app/node_modules ./node_modules
COPY . .

EXPOSE 7000
ENTRYPOINT ["node","server.js"]