# (Japanese) ARM (M1) Mac に Python `psycopg2` をインストールする手順まとめ

ARM (M1) Mac 上の Docker (Docker for Mac) で Python パッケージ `psycopg2` をインストールするための手順のまとめです。

| ベースイメージ | サンプルディレクトリ |
| --- | --- |
| `debian:bookworm` | [`debian-bookworm/`](./debian-bookworm/) |
| `debian:bullseye` | [`debian-bullseye/`](./debian-bullseye/) |
| `python:3.10` | [`python-3.10/`](./python-3.10/) |
| `python:3.10-alpine` | [`python-3.10-alpine/`](./python-3.10-alpine/) |
| `ubuntu:20.04` | [`ubuntu-20.04/`](./ubuntu-20.04/) |
| `ubuntu:22.04` | [`ubuntu-22.04/`](./ubuntu-22.04/) |

`python:3.10` の場合はそのまま `psycopg2` をインストールするだけで OK です:

```zsh
python3 -m pip install psycopg2
```

`python:3.10-alpine` の場合は `apk` で `gcc` `musl-dev` `postgresql-dev` などを入れる必要があります:

```zsh
apk add gcc musl-dev postgresql-dev
```

`debian` や `ubuntu` の場合はもう少し多くのパッケージを入れる必要があります:

```zsh
apt-get install -y --no-install-recommends \
    build-essential \
    libpq-dev \
    python3 \
    python3-dev \
    python3-pip
```

詳細はサブディレクトリの各 `Dockerfile` を参照してください。

