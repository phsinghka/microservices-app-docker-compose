FROM node:16 as build

WORKDIR /usr/src/app

COPY ./package*.json .

RUN npm install

COPY . .

FROM node:16-alpine

WORKDIR /usr/src/app

COPY --from=build /usr/src/app .

EXPOSE 5000

CMD [ "node", "server.js" ]
