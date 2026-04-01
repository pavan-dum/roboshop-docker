FROM node:20
#RUN mkdir /app

#this creates and move to app dir
WORKDIR /app

COPY package.json .
COPY *.js .

RUN npm install


ENV MONGO="true" /
    MONGO_URL="mongodb://mongodb:27017/catalogue

CMD ["node", "server.js"]