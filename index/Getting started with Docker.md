
## Getting started with Docker


Here's a general overview of [Docker for beginners]()(https://prakhar.me/docker-curriculum/).

And here's a [cheat sheet]()(https://www.docker.com/sites/default/files/Docker\_CheatSheet\_08.09.2016\_0.pdf) with basic Docker commands.

In case you're interested, here's a [handy overview]()(https://docs.docker.com/engine/userguide/eng-image/dockerfile\_best-practices/) of best practices for creating Docker containers.


View currently running docker containers:

```
`docker ps
```
`
Close and delete all currently running Docker containers:

```
`docker rm -f $(docker ps -aq)
```

Launch Docker container for this course:

```
`mkdir /Desktop/sharedfolder

docker pull stevemclaugh/audio-ml-notebook

docker run -it --name audio_ml_container2 -p 8888:8888 -v /Desktop/sharedfolder:/home/sharedfolder stevemclaugh/audio-ml-notebook
```
\`
You can view the Dockerfile we're using to build our container [here]()(https://github.com/stevemclaugh/audio-ml-notebook/blob/master/Dockerfile).

