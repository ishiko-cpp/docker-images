FROM alpine:3.23.2

RUN apk add boost-dev
RUN apk add build-base
RUN apk add cmake
RUN apk add git

WORKDIR /ishiko/third-party/fmtlib

RUN git clone https://github.com/ishiko-third-party/fmtlib_fmt.git fmt
RUN cd fmt && mkdir build && cd build && cmake .. && make && make install

WORKDIR /ishiko/third-party/randombit

ENV BOTAN_ROOT=/ishiko/third-party/randombit/botan
RUN git clone https://github.com/ishiko-third-party/randombit_botan.git botan
RUN cd botan && git checkout 2.19.5-fix && python3 configure.py --prefix=${BOTAN_ROOT} --disable-shared-library && make && make install

WORKDIR /ishiko/third-party

ENV PUGIXML_ROOT=/ishiko/third-party/pugixml
RUN git clone https://github.com/ishiko-third-party/pugixml.git

WORKDIR /ishiko/third-party/no1msd

RUN git clone https://github.com/ishiko-third-party/no1msd_mstch.git mstch
RUN cd mstch && mkdir build && cd build && cmake .. && make && make install
