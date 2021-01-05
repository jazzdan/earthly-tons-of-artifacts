FROM node:14.15.0
WORKDIR /usr/build

docker-setup:
    COPY lib/* .
    ARG service
    COPY src/build/Dockerfile.${service} Dockerfile
    SAVE ARTIFACT ./*

standalone-local:
    FROM --build-arg service=standalone +docker-setup
    SAVE ARTIFACT ./* AS LOCAL out/standalone/