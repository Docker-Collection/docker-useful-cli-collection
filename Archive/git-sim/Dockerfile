FROM python:3.11.1-buster as Builder

WORKDIR /workdir
COPY entrypoint.sh .

RUN apt-get update && \
    apt-get install -y libsdl-pango-dev ffmpeg && \
    pip install --no-cache-dir manim && \
    pip install --no-cache-dir git-sim && \
    rm -rf /var/cache/apt/archives /var/lib/apt/lists/* && \
    chmod +x entrypoint.sh

ENTRYPOINT [ "sh", "/entrypoint.sh" ]

# FROM python:3.10.9-alpine@sha256:ca1298a74c3495b6bc539044352301fa371f6e10b0e085f93d2a4ef3e4c3fa6c

# COPY --from=Builder /root/.local /root/.local

# ENV PATH=/root/.local/bin:$PATH

# ENTRYPOINT [ "git-sim" ]