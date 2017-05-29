# Audio ML Notebook
#
# FFmpeg installer adapted from https://hub.docker.com/r/nedward/docker-ffmpeg/~/dockerfile/
# MAINTAINER Ned Harris <nedward777@gmail.com>

FROM ubuntu:14.04

MAINTAINER Steve McLaughlin <stephen.mclaughlin@utexas.edu>

# Make sure ubuntu is up to date
RUN apt-get update -y

# Install dependancies

RUN apt-get -y install python python3 python-pip python3-pip
RUN pip install --upgrade pip

RUN pip install -U setuptools
RUN pip install jupyter
RUN python2 -m pip install ipykernel
