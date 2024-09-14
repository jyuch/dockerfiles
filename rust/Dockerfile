FROM rust:1.81.0-slim AS build

WORKDIR /app

RUN --mount=type=bind,source=src,target=src \
    --mount=type=bind,source=Cargo.toml,target=Cargo.toml \
    --mount=type=bind,source=Cargo.lock,target=Cargo.lock \
    --mount=type=cache,target=/app/target/ \
    --mount=type=cache,target=/usr/local/cargo/git/db \
    --mount=type=cache,target=/usr/local/cargo/registry \
    set -eux; \
    cargo build --locked --release; \
    cp ./target/release/hello_rust /bin/hello_rust

FROM debian:stable-slim AS final
COPY --from=build /bin/hello_rust /bin/hello_rust
ENTRYPOINT ["/bin/hello_rust"]

