FROM node:16.20.1-alpine3.18

RUN mkdir -p /usr/app

COPY package*.json /usr/app/
COPY app/* /usr/app/

WORKDIR /usr/app

RUN npm install
CMD ["node", "server.js"]