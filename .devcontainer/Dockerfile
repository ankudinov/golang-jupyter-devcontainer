# FROM mcr.microsoft.com/vscode/devcontainers/base:alpine-3.14
FROM mcr.microsoft.com/devcontainers/go:0-1-bullseye

# install jupyter notebook
RUN apt-get update \
    && apt-get install -y --no-install-recommends python3-pip \
    # ipykernel depends on pusutil, which does not publish wheels for aarch64
    # source https://github.com/awslabs/amazon-emr-vscode-toolkit/pull/5/files
    && if [ "$TARGETARCH" != "amd64" ]; then apt-get install -y --no-install-recommends gcc python3-dev; fi \
    && pip3 install jupyter notebook pyzmq tornado ipykernel

# install gophernotes
USER vscode
RUN go install github.com/gopherdata/gophernotes@v0.7.5 \
    && mkdir -p ~/.local/share/jupyter/kernels/gophernotes \
    && cd ~/.local/share/jupyter/kernels/gophernotes \
    && cp "$(go env GOPATH)"/pkg/mod/github.com/gopherdata/gophernotes@v0.7.5/kernel/*  "." \
    && chmod +w ./kernel.json \
    && sed "s|gophernotes|$(go env GOPATH)/bin/gophernotes|" < kernel.json.in > kernel.json

EXPOSE 8888
