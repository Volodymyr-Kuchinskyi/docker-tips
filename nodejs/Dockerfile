FROM node:10.16-alpine

EXPOSE 3000

RUN apk add --no-cache tini

WORKDIR /app

COPY package*.json .

RUN npm install && npm cache clean --force

COPY . .

ENTRYPOINT ["/sbin/tini", "--"]

CMD ["node", "app"]
