FROM python:3.6.5

MAINTAINER Luis Mayta <@slovacus>

LABEL NAME python
LABEL VERSION 3.6.5

COPY ./requirements/ /usr/src/requirements/
COPY ./requirements.txt /usr/src/requirements.txt

# set working directory to /usr/src/
WORKDIR /usr/src/

RUN pip install -r /usr/src/requirements/dev.txt
