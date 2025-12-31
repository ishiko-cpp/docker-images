FROM ishiko/alpine-ishiko-cpp-build-prerequisites:0.6.0

ENV ISHIKO_CPP_ROOT=/ishiko/cpp

WORKDIR /ishiko/cpp

RUN git clone https://github.com/ishiko-cpp/base-platform.git
RUN cd base-platform/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/errors.git
RUN cd errors/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/memory.git
RUN cd memory/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/logging.git
RUN cd logging/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/types.git
RUN cd types/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/hash.git
RUN cd hash/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/synchronization.git
RUN cd synchronization/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/data-structures.git
RUN cd data-structures/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/collections.git
RUN cd collections/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/text.git
RUN cd text/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/time.git
RUN cd time/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/concurrency.git
RUN cd concurrency/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/process.git
RUN cd process/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/io.git
RUN cd io/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/filesystem.git
RUN cd filesystem/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/xml.git
RUN cd xml/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/json.git
RUN cd json/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/yaml.git
RUN cd yaml/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/diff.git
RUN cd diff/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/configuration.git
RUN cd configuration/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/test-framework.git
RUN cd test-framework/core/build-files/gnumake && make
RUN cd test-framework/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/crypto.git
RUN cd crypto/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/terminal.git
RUN cd terminal/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/workflows.git
RUN cd workflows/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/uuids.git
RUN cd uuids/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/networking.git
RUN cd networking/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/http.git
RUN cd http/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/rest.git
RUN cd rest/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/csv.git
RUN cd csv/build-files/gnumake && make

RUN git clone https://github.com/ishiko-cpp/pdf.git
RUN cd pdf/build-files/gnumake && make

WORKDIR /
