FROM node:14.14.0-alpine
RUN mkdir -p /app
WORKDIR /app
COPY package.json /app
COPY .env.example .env
COPY . /app
RUN npm install
CMD ["npm", "run", "start"]

EXPOSE 3500