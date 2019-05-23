FROM alpine:3.9
LABEL maintainer="c.torsday@gmail.com"

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apk add --update --no-cache \
    python3 \
    python3-dev \
    py3-pip \
    build-base \
  && pip3 install --upgrade pip setuptools \
  && rm -rf /var/cache/apk/*

RUN mkdir -p /mutable_data
RUN mkdir -p /shared_data
RUN mkdir -p /src
COPY ./requirements.txt /requirements.txt

WORKDIR /

RUN pip3 install -r requirements.txt

CMD exec python3 /src/main.py
