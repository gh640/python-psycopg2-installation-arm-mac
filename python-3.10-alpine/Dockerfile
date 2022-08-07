FROM python:3.10-alpine

RUN apk update && \
  apk add \
    gcc \
    musl-dev \
    postgresql-dev \
    && \
  rm -rf /var/cache/apk/*

RUN python3 -m pip install psycopg2
