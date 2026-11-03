ARG VARIANT=3.12-bookworm
FROM mcr.microsoft.com/devcontainers/python:${VARIANT}

ENV PYTHONUNBUFFERED=1

# Remove the old Yarn package source if present (its signing key can expire and break apt)
RUN rm -f /etc/apt/sources.list.d/yarn.list

RUN apt-get update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends postgresql-client \
    && rm -rf /var/lib/apt/lists/*
