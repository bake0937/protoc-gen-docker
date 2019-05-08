FROM node:11.14.0

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
