# 開発環境
FROM rust:1.67-slim-bullseye
RUN apt-get update && apt-get -y install \ 
  build-essential \
  git \
  clang \
  cmake \
  libstdc++-10-dev \
  libssl-dev \
  libxxhash-dev \
  zlib1g-dev \
  pkg-config \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/*
RUN git clone https://github.com/rui314/mold.git \
  && cd mold \
  && git checkout v1.0.3 \
  && make -j$(nproc) CXX=clang++ \
  && make install
RUN cargo install --locked --version=7.8.0 cargo-watch && \
  rustup component add rustfmt


