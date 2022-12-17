FROM node:12.22.0-alpine

WORKDIR /usr/src/app


COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 80

CMD [ "node", "server.js" ]