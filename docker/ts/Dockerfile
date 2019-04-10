FROM node:11.12.0-alpine

RUN apk add --update \
    && apk add make gcc g++ \
    && apk add --no-cache protobuf curl \
    && mkdir -p /protobuf/google/protobuf \
    && for f in any duration descriptor empty struct timestamp wrappers; do \
         curl -L -o /protobuf/google/protobuf/${f}.proto https://raw.githubusercontent.com/google/protobuf/master/src/google/protobuf/${f}.proto; \
       done \
    && apk del curl \
    && rm -rf /var/cache/apk/*

RUN npm i ts-protoc-gen@0.9.0
RUN npm i google-protobuf@3.7.1