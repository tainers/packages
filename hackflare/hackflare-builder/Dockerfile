FROM elixir:1.19-alpine

# System deps for Elixir + Rust + NIFs
RUN apk add --no-cache \
    build-base \
    git \
    curl \
    openssl-dev \
    pkgconfig \
    ncurses-dev

# Install Rust (musl target by default on Alpine)
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | \
    sh -s -- -y

ENV PATH="/root/.cargo/bin:${PATH}"

ENV MIX_ENV=prod \
    LANG=C.UTF-8

# Preinstall Hex + Rebar
RUN mix local.hex --force && \
    mix local.rebar --force