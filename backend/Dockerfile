FROM node:alpine3.18

WORKDIR /mern-chatbot/backend 

COPY package.json .

RUN apk update && \
    apk upgrade && \
    npm update -g && \
    npm install && \
    npm cache clean --force

COPY . .

EXPOSE 5001

CMD npm run build && npm start
