FROM debian:9

RUN apt-get update -yq \
   && apt-get install curl gnupg -yq \
   && curl -sL https://deb.nodesource.com/setup_10.x | bash \
   && apt-get install nodejs -yq \
   && apt-get clean -y
ENV NODE_ENV production

RUN mkdir -p /app

WORKDIR /app

COPY package.json .
COPY yarn.lock .

RUN npm install
COPY . /app

EXPOSE 3500

CMD ["node", "app.js"]