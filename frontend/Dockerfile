FROM node:18-alpine3.14
WORKDIR /My_Classmate
COPY package.json package-lock.json /My_Classmate/
RUN npm install
COPY  . .
RUN npm run build