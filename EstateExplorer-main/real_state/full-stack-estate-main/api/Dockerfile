FROM ubuntu:latest

RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash -
RUN apt-get install -y nodejs

WORKDIR /app
COPY package.json package.json

RUN npm i
RUN npm i -g nodemon
RUN npm i -g prisma

COPY . . 
RUN npx prisma generate
EXPOSE 8800


CMD ["nodemon","app.js"]