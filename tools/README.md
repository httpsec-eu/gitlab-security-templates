# Dockerfile

This folder contains the Dockerfile to build the image used in the article to run the Syft app.


## Usage

```bash
export IMAGE="dependency-scan:1.0"
export BASE_IMAGE='alpine:3.19.1' 
export SYFT_VER='v0.105.0'
export GRYPE_VER='v0.74.4'
export DOCKER_REPO='denisrendler'

docker build -t ${DOCKER_REPO}/$IMAGE \
    -f Dockerfile . \
    --build-arg "BASE_IMAGE=${BASE_IMAGE}" \
    --build-arg "GIT_VERSION=1.0" \
    --build-arg "SYFT_VER=${SYFT_VER}" \
    --build-arg "GRYPE_VER=${GRYPE_VER}"

```
