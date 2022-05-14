FROM rust:1.60.0-slim
LABEL maintainer = "Chihiro Hasegawa <encry1024@gmail.com>"

RUN apt-get update -y && apt-get install -y \
build-essential pkg-config libssl-dev

RUN cargo install cargo-edit

WORKDIR /mnt