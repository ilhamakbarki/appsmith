FROM node:14

USER root
RUN npm i -g npx
RUN npm i -g yarn

WORKDIR /app

COPY . .

RUN yarn install

EXPOSE 3000

CMD [ "yarn", "run", "start" ]
