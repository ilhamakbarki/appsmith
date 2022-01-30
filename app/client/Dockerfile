FROM node:14

USER root

WORKDIR /app

COPY . .

RUN yarn install

EXPOSE 3000

CMD [ "yarn", "run", "start" ]
