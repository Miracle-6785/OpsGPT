FROM node:alpine3.18

WORKDIR /mern-chatbot/backend 

COPY package.json .

RUN npm install 

COPY . .

EXPOSE 5001

CMD npm run build && npm start