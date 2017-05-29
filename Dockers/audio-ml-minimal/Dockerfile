    # Audio ML Notebook
#
# FFmpeg installer adapted from https://hub.docker.com/r/nedward/docker-ffmpeg/~/dockerfile/
# MAINTAINER Ned Harris <nedward777@gmail.com>

FROM ubuntu:14.04
# FROM jupyter/minimal-notebook

EXPOSE 8888

MAINTAINER Steve McLaughlin <stephen.mclaughlin@utexas.edu>

# Make sure ubuntu is up to date
RUN apt-get update -y

RUN apt-get install -y wget

# Install Tini
RUN wget --quiet https://github.com/krallin/tini/releases/download/v0.10.0/tini && \
    echo "1361527f39190a7338a0b434bd8c88ff7233ce7b9a4876f3315c22fce7eca1b0 *tini" | sha256sum -c - && \
    mv tini /usr/local/bin/tini && \
    chmod +x /usr/local/bin/tini

# Install FFmpeg with mp3 support
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:mc3man/trusty-media
RUN apt-get update -y
RUN apt-get install -y ffmpeg gstreamer0.10-ffmpeg

RUN apt-get -y install python2.7 python-pip python-dev
RUN apt-get -y install ipython ipython-notebook
RUN pip install --upgrade pip
RUN apt-get install -y libffi-dev libssl-dev

RUN pip install -U six==1.6.0
RUN pip install requests==2.5.3

RUN pip install -U jupyter numpy scipy matplotlib pandas

RUN pip install -U sklearn=0.18 pydub tqdm requests

RUN pip install pyAudioAnalysis


# Configure container startup
ENTRYPOINT ["tini", "--"]
CMD ["cd /home && jupyter notebook --ip 0.0.0.0 --no-browser --allow-root"]
