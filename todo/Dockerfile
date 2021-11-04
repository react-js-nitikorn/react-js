FROM node:16-buster as dev
WORKDIR $SOURCE
COPY package.json package.json
COPY yarn.lock yarn.lock
COPY  . .
RUN yarn 
RUN yarn build --profile

FROM nginx:1.21.3-alpine 
COPY --from=dev /to-do/build/ /usr/share/nginx/html
EXPOSE 80



