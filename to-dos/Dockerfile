FROM node:17-buster
WORKDIR /to-dos         
COPY package.json package.json
COPY yarn.lock yarn.lock
RUN npm install
RUN npm audit fix --force
COPY . .
CMD ["yarn","start"]
