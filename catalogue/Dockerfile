#stage 1: Build
FROM node:20-alpine AS builder
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install


#stage 2: Runtime
FROM node:20-alpine
WORKDIR /app
EXPOSE 8080

COPY --from=builder /app /app

ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"

RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN chown -R roboshop:roboshop /app
USER roboshop

CMD ["node", "server.js"]

#server.js is a argument
#ENTRYPOINT ["node"]  # node is a command