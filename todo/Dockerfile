FROM node:16-buster as dev
ARG SOURCE
ENV SOURCE=${SOURCE}
WORKDIR SOURCE
COPY SOURCE/ SOURCE/
RUN echo ${SOURCE}
# COPY package.json package.json
# COPY yarn.lock yarn.lock

# RUN yarn
# RUN yarn build --profile

# FROM nginx:1.21.3-alpine 
# COPY --from=dev /to-do/build/ /usr/share/nginx/html
# EXPOSE 80



