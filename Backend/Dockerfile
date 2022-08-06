FROM node:14-alpine

ENV NODE_ENV production

RUN mkdir -p /app

WORKDIR /app

COPY package.json /app
COPY yarn.lock /app

RUN npm install -g npm@8.16.0
RUN npm install --only=production

COPY . /app

EXPOSE 3500

CMD ["node", "app.js"]