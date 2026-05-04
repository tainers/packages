FROM elixir:1.19-slim

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    curl \
    ca-certificates \
    openssl \
    pkg-config \
    libssl-dev \
 && update-ca-certificates \
 && rm -rf /var/lib/apt/lists/*

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | \
    sh -s -- -y

ENV PATH="/root/.cargo/bin:${PATH}"

ENV MIX_ENV=prod \
    LANG=C.UTF-8

RUN mix local.hex --force && \
    mix local.rebar --force