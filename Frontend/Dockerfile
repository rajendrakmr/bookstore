#stage 1
FROM node:20 AS builder

WORKDIR /app

COPY . /app

RUN npm install

RUN npm run dev

EXPOSE 5173

CMD [ "node","dev" ]

