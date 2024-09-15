FROM amazonlinux:2023

RUN echo "keepcache=True" >> /etc/dnf/dnf.conf

RUN --mount=type=cache,target=/var/cache/dnf \
    --mount=type=cache,target=/var/lib/dnf \
    dnf install -y \
      gcc gcr lvm2 clang
