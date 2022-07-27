FROM node:12.18.1 as build-stage
RUN mkdir -p /app
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app
# ARG REACT_APP_BASEURL
# ENV REACT_APP_API_BASE_URL=$REACT_APP_API_BASE_URL
RUN npm run start

#FROM nginx:1.17.0-alpine
#COPY --from=build-stage /Frontend/build /usr/share/nginx/html
#EXPOSE 3000
#CMD nginx -g 'daemon-off;'