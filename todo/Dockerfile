FROM node:16-buster as dev
ARG SOURCE
ENV SOURCE=${SOURCE}
WORKDIR SOURCE
COPY . .
RUN yarn --version
RUN npm install
RUN npm audit fix --force
RUN yarn build --profile

FROM nginx:1.21.3-alpine 
ARG SOURCE
ENV SOURCE=${SOURCE}
COPY --from=dev /${SOURCE}/build/ /usr/share/nginx/html
EXPOSE 80



