# -*- mode: dockerfile -*-
#
# An example Dockerfile showing how to add new static C libraries using
# musl-gcc.

FROM jiangxiaoqiang/rust-musl-builder

# Build a static copy of zlib.
#
# EXAMPLE ONLY! libz is already included.
RUN VERS=1.2.13 && \
    cd /home/rust/libs && \
    curl -LO http://zlib.net/fossils/zlib-$VERS.tar.gz && \
    tar xzf zlib-$VERS.tar.gz && cd zlib-$VERS && \
    CC=musl-gcc ./configure --static --prefix=/usr/local/musl && \
    make && sudo make install && \
    cd .. && rm -rf zlib-$VERS.tar.gz zlib-$VERS
