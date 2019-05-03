FROM alpine:latest

# 
RUN apk update && apk add --no-cache --virtual .build-deps \
    gcc \
    python3-dev \
    musl-dev \
    libxslt-dev \
    libxml2-dev \
    postgresql-dev \
    openssh-client \
    alpine-sdk \
    openblas-dev \
    gfortran \
    git

# 
RUN apk update && apk add --no-cache \
    postgresql \
    libxslt \
    libxml2 \
    libstdc++ \
    mc \
    py3-lxml \
    openblas \
    cython

# python packages
RUN pip3 install --no-cache-dir \
    pandas \
    numpy \
    scipy