FROM debian:bookworm

RUN apt-get update && \
  apt-get install -y --no-install-recommends \
    build-essential \
    libpq-dev \
    python3 \
    python3-pip \
    python3-dev \
    && \
    rm -rf /var/lib/apt/lists/*

RUN python3 -m pip install psycopg2
