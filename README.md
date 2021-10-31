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
 ### Caching
  
 ### Optimize Base Image
  
 ### Support Multi ENV (Runtime ENV)
 
 ### Container Hardening

 ### CircleCI
[**Configuration**](https://circleci.com/docs/2.0/configuration-reference/)
 > This document is a reference for the CircleCI 2.x configuration keys that are used in the config.yml file. The presence of a .circleci/config.yml file in your CircleCI-authorized repository branch indicates that you want to use the 2.x infrastructure.
 

## References
### Caching
  1. [Docker Tutorial - Improve Docker builds with Caching and Layers](https://www.youtube.com/watch?v=dSpOBSRJFwg)
  2. [Intro Guide to Dockerfile Best Practices](https://www.docker.com/blog/intro-guide-to-dockerfile-best-practices/)
  3. [Docker Layer Caching](https://docs.semaphoreci.com/ci-cd-environment/docker-layer-caching/)
 ### Optimize Base Image
  1. [Top 20 Dockerfile best practices](https://sysdig.com/blog/dockerfile-best-practices/)
 ### Support Multi ENV (Runtime ENV)
  1. [Docker multi-stage build and environment variables](https://dev.to/migsarnavarro/docker-multi-stage-build-and-environment-variables-4lp2)
 ### Container Hardening
 1. [Container security best practices: Comprehensive guide](https://sysdig.com/blog/container-security-best-practices/)