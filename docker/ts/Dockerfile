FROM node:11.14.0

# RUN apk add --update \
#     && apk add make gcc g++ git
    # && apk add --no-cache protobuf curl \
    # && mkdir -p /protobuf/google/protobuf \
    # && for f in any duration descriptor empty struct timestamp wrappers; do \
    #      curl -L -o /protobuf/google/protobuf/${f}.proto https://raw.githubusercontent.com/google/protobuf/master/src/google/protobuf/${f}.proto; \
    #    done \
    # && apk del curl \
    # && rm -rf /var/cache/apk/*

RUN npm i git

RUN git clone https://github.com/google/protobuf.git -b v3.7.1 --depth 1 && \
    cd protobuf && \
    ./autogen.sh && \
    ./configure && \
    make -j4 && \
    make -j4 install && \
    ldconfig && \
    make clean && \
    cd .. && \
    rm -r protobuf
  

RUN npm i google-protobuf@3.7.1
RUN npm i ts-protoc-gen@next
