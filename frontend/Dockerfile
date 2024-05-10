# Stage 1: Build frontend
FROM node:alpine3.18 AS build-stage

WORKDIR /mern-chatbot/frontend

COPY package.json .

RUN npm install 

COPY . .

# ARG REACT_APP_API_BASE_URL
# ENV REACT_APP_API_BASE_URL=${REACT_APP_API_BASE_URL}

RUN npm run build

# Stage 2: Serve frontend with nginx
# FROM nginx:latest
FROM node:alpine3.18 AS product-image

WORKDIR /mern-chatbot/frontend

# is /mern-chatbot/frontend/dist correct instead of /mern-chatbot/frontend/build ?
COPY --from=build-stage /mern-chatbot/frontend/dist /mern-chatbot/frontend/dist

COPY package.json .

COPY vite.config.ts .

RUN npm install typescript

EXPOSE 5173

CMD npm run preview

# CMD ["nginx", "-g", "daemon off;"]