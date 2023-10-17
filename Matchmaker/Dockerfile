FROM node:18.17-bullseye

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
RUN npm install run-script-os
COPY . .
EXPOSE 90 9090

CMD [ "node", "matchmaker.js"]
