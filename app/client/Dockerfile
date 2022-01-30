FROM node:14

USER root
RUN npm i -g npx
RUN npm i -g yarn

WORKDIR /app

COPY . .

RUN yarn install

ENV APPSMITH_SERVER_PROXY_PASS="http://appsmith-internal-server:8080"
EXPOSE 3000

CMD [ "yarn", "run", "start" ]
