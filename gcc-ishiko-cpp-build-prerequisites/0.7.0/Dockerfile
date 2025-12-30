ARG INSTALL_DIR="/workspace/installation"

# Image used to build cmake
FROM gcc:15.2.0 AS build-cmake

ARG INSTALL_DIR

WORKDIR /projects/Kitware

RUN git clone https://github.com/ishiko-third-party/Kitware_CMake.git CMake
RUN cd CMake && ./bootstrap --prefix=${INSTALL_DIR} && make && make install


# Image used to build the rest of the dependencies
FROM gcc:15.2.0 AS build-dependencies

ARG INSTALL_DIR

# Install cmake because it is needed to build some of the dependencies
COPY --from=build-cmake ${INSTALL_DIR} /usr/local

WORKDIR /projects

RUN wget https://archives.boost.io/release/1.90.0/source/boost_1_90_0.tar.bz2
RUN tar xjf boost_1_90_0.tar.bz2

WORKDIR /projects/boost_1_90_0

RUN ./bootstrap.sh --prefix=${INSTALL_DIR}
RUN ./b2 install

WORKDIR /ishiko/third-party/fmtlib

RUN git clone https://github.com/ishiko-third-party/fmtlib_fmt.git fmt
RUN cd fmt && mkdir build && cd build && cmake -DCMAKE_INSTALL_PREFIX=${INSTALL_DIR} .. && make && make install


# Final image containing the necessary dependencies stripped of all the build artifacts
FROM gcc:15.2.0

ARG INSTALL_DIR

COPY --from=build-cmake ${INSTALL_DIR} /usr/local
COPY --from=build-dependencies ${INSTALL_DIR} /usr/local
RUN ldconfig

WORKDIR /ishiko/third-party/randombit

ENV BOTAN_ROOT=/ishiko/third-party/randombit/botan
RUN git clone https://github.com/ishiko-third-party/randombit_botan.git botan
RUN cd botan && git checkout 2.19.5-fix && python3 configure.py --prefix=${BOTAN_ROOT} --disable-shared-library && make && make check && make install

WORKDIR /ishiko/third-party

ENV PUGIXML_ROOT=/ishiko/third-party/pugixml
RUN git clone https://github.com/ishiko-third-party/pugixml.git

WORKDIR /ishiko/third-party/no1msd

RUN git clone https://github.com/ishiko-third-party/no1msd_mstch.git mstch
RUN cd mstch && mkdir build && cd build && cmake .. && make && make install
