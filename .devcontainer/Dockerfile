# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.183.0/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version: buster, stretch
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

ARG USER=vscode

# ** [Optional] Uncomment this section to install additional packages. **
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
     && apt-get -y install --no-install-recommends \
            sudo \
            pkg-config \
            git \
            build-essential \
            m4 \
            software-properties-common \
            aspcud \
            unzip \
            rsync \
            curl \
            dialog \
            nano \
            libx11-dev \
            rsync \
    && apt-get clean -y

USER $USER
ENV PATH=$PATH:$HOME/.opam/system/bin/

RUN opam init \
    && eval `opam config env`
