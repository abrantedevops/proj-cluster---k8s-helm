FROM node:16

WORKDIR /app

COPY package*.json ./

RUN mkdir /app/public
COPY script/ /app/script

# Archive data.zip sqlite find here: https://github.com/strapi/foodadvisor/tree/master/api
COPY data.zip /app/data.zip

RUN npm install

RUN yarn && yarn seed && yarn develop

COPY . .

EXPOSE 1337

CMD [ "npm", "start" ]
