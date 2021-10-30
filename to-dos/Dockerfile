FROM node:17-buster
WORKDIR /to-dos         
COPY package.json package.json
COPY yarn.lock yarn.lock
RUN yarn

COPY . .
CMD ["yarn","start"]