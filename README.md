# PanWriter Docker

This repository allows you to contribute to [PanWriter](https://www.panwriter.com)
with all the required stuff being located in a docker container.

## Using Docker Compose

Install Docker and Docker Compose for your system, then:

    git clone https://github.com/Skeeve/panWriterDocker.git

Aloso check out panwriter. Either the original repository or your fork.

    git clone https://github.com/mb21/panwriter.git

Please note that `panWriterDocker` and `panwriter` are located
in the same directory.
This is mandatory for `panWriterDocker` to work.
Should you want to have `panwriter` be located elsewhere,
you have to adjust the relative path in `docker-compose.yaml`.

    cd panWriterDocker
    docker compose build

This will prepare a docker image, which can be used for development.

#### Start an interactive bash shell

    docker compose run --rm -it panwriter

The directories

- `../panwriter/src`
- `../panwriter/electron`
- `dist`

are bound into the container.
So any change you make to the source with your preferred editor
will be available in the container where you then can run the
development server or build the application.

#### useful commands

Build for

    docker compose run --rm panwriter yarn dist        # Linux
    docker compose run --rm panwriter yarn dist -w     # Windows
    docker compose run --rm panwriter yarn dist -m zip # Mac OS

The distribution files can be found in `panWriterDocker`´s `dist` directory.

Start development server

    docker compose up panserver

## Powered by

`panWriterDocker` is powered by:

- [electron-userland/electron-builder](https://github.com/electron-userland/electron-builder)
- [Docker](https://www.docker.com)
