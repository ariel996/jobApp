FROM node:14-alpine as builder

RUN mkdir -p /app
WORKDIR /app

COPY package.json /app
COPY yarn.lock /app
COPY . /app

RUN npm install
RUN npm run build
# CMD ["npm", "build"]

# Bundle static assets with nginx
FROM nginx as production
ENV NODE_ENV production
# Add your nginx.conf
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# Copy built assets from builder
COPY --from=builder /app/build /usr/share/nginx/html
# Expose port
EXPOSE 80
# Start nginx
CMD ["nginx", "-g", "daemon off;"]