FROM python:3.6.1

MAINTAINER Luis Mayta <@slovacus>

LABEL NAME check
LABEL VERSION 1.0.1

COPY ./requirements/ /usr/src/requirements/
COPY ./requirements.txt /usr/src/requirements.txt

# set working directory to /usr/src/
WORKDIR /usr/src/

RUN apt-get update -y \
    && apt-get -y install --no-install-recommends \
    # tools validation
    shellcheck \
    # install python dependencies
    && pip install -r /usr/src/requirements/setup.txt \
    && apt-get purge \
    && rm -rf /var/lib/apt/lists/*
