[![CircleCI](https://circleci.com/gh/react-js-nitikorn/react-js/tree/main.svg?style=svg)](https://circleci.com/gh/react-js-nitikorn/react-js/tree/main)
# React-js
ทำการสร้าง **Github Organization** เป็นของตัวเอง จากนั้นเข้า **Circle CI แล้ว Grant** สิทธิ์ให้เรียบร้อย (เชื่อม Circle Ci + Git Org) เขียน **Pipeline** ในการทำ **Containerize** 
React js

 - [ ]  ทำ Caching
 - [ ]  Optimize Base Image
 - [ ]  Support Multi ENV (Runtime ENV)
 - [ ]  Container Hardening
 # Documentation
 ## React
 > [To-dos app](https://ibaslogic.com/react-tutorial-for-beginners/)

 **Create Project**
 ```
 npx create-react-app todos
 ```
 **Run Initial todos**
 > default default port 3000
 ```
 yarn start
 ```
 ## Docker
 ### 1. Caching
 **1.1 Circle CI**

 > What is the Caching that is the process of storing data in a [cache](https://searchstorage.techtarget.com/definition/cache).
 On this project, we will talk about [the Docker Layer Caching (DLC)](https://circleci.com/docs/2.0/docker-layer-caching/) that can reduce Docker image build times on CircleCI.
 > [docker_layer_caching: true](https://circleci.com/docs/2.0/docker-layer-caching/#configyml)
 ```
 version: 2
jobs:
  build_elixir:
    machine:
      image: ubuntu-2004:202104-01
      docker_layer_caching: true
    steps:
      - checkout
      - run:
          name: build Elixir image
          command: docker build -t circleci/elixir:example .
 ```
 **1.2 Docker caching**

 Indeep about [Images and layers](https://docs.docker.com/storage/storagedriver/)
![](https://docs.docker.com/storage/storagedriver/images/container-layers.jpg)

 How to [Leverage build cache](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#leverage-build-cache)
 ### 2. Optimize Base Image
  If I have issue about how to optimize base image, I usually use [the multistage builds](https://docs.docker.com/develop/develop-images/multistage-build/) that are useful to anyone who has struggled to optimize Dockerfiles while keeping them easy to read and maintain.

  [Use multi-stage build](https://docs.docker.com/develop/develop-images/multistage-build/#use-multi-stage-builds)
  
  **Dockerfile**
  ```
 FROM node:16-buster as dev
 WORKDIR /to-do
 COPY package.json package.json
 COPY yarn.lock yarn.lock
 COPY  . .
 RUN yarn 
 RUN yarn build --profile

 FROM nginx:1.21.3-alpine 
 COPY --from=dev /to-do/build/ /usr/share/nginx/html
 EXPOSE 80

  ```
 ### 3. Support Multi ENV (Runtime ENV)
 
 ### 4. Container Hardening

 ### 5. CircleCI
[**Configuration**](https://circleci.com/docs/2.0/configuration-reference/)
 > This document is a reference for the CircleCI 2.x configuration keys that are used in the config.yml file. The presence of a .circleci/config.yml file in your CircleCI-authorized repository branch indicates that you want to use the 2.x infrastructure.
 ```
 version: 2.1
jobs:
  build:
    docker:
      - image: alpine:3.7
    steps:
      - run:
          name: The First Step
          command: |
            echo 'Hello World!'
            echo 'This is the delivery pipeline'
 ```
## References
### Caching
  1. [Docker Tutorial - Improve Docker builds with Caching and Layers](https://www.youtube.com/watch?v=dSpOBSRJFwg)
  2. [Intro Guide to Dockerfile Best Practices](https://www.docker.com/blog/intro-guide-to-dockerfile-best-practices/)
  3. [Docker Layer Caching](https://docs.semaphoreci.com/ci-cd-environment/docker-layer-caching/)
  4. [Best practices for writing Dockerfiles](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
 ### Optimize Base Image
  1. [Top 20 Dockerfile best practices](https://sysdig.com/blog/dockerfile-best-practices/)
 ### Support Multi ENV (Runtime ENV)
  1. [Docker multi-stage build and environment variables](https://dev.to/migsarnavarro/docker-multi-stage-build-and-environment-variables-4lp2)
 ### Container Hardening
 1. [Container security best practices: Comprehensive guide](https://sysdig.com/blog/container-security-best-practices/)
