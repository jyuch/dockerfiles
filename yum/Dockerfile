FROM amazonlinux:2

RUN sed -i -e 's/keepcache=0/keepcache=1/' /etc/yum.conf
RUN echo "test5"
RUN --mount=type=cache,target=/var/cache/yum \
    yum install -y \
      gcc gcr lvm2 clang
