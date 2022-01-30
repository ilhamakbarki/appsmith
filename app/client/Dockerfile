FROM node:14 as builder

USER root

WORKDIR /app

COPY . .

RUN yarn install

RUN yarn build


FROM nginx:1.20-alpine

COPY --from=builder ./build /var/www/appsmith

EXPOSE 80

COPY ./docker/templates/nginx-root.conf.template /nginx-root.conf.template

COPY ./docker/templates/nginx-app-http.conf.template /nginx-app-http.conf.template
COPY ./docker/templates/nginx-app-https.conf.template /nginx-app-https.conf.template

# This is the script that is used to start Nginx when the Docker container starts
COPY ./docker/start-nginx.sh /start-nginx.sh
CMD ["/start-nginx.sh"]
