
## Audio bundle
    - sine wave
    - clarinet recording
    - guitar
    - drum
    - speech recording
    - music recordings


# In Class

## Install a text editor

- macOS: https://atom.io/



## Set up Docker containers

- Install Docker

Install Docker Toolbox for macOS and Windows: https://www.docker.com/products/docker-toolbox

Or install Docker Community Edition for Linux: https://store.docker.com/search?type=edition&offering=community

> Docker for Beginners: https://prakhar.me/docker-curriculum/




- Install Kitematic
- Download docker containers


```bash
cd /path/to/audio-ml-minimal
docker build -t audio-ml-minimal:audioml ./

docker run --name audioml -it -p 8888:8888 -v ~/Desktop/sharedfolder:/home/sharedfolder bash
```

`audioml` is the name of the container instance we're launching.


In the Docker shell:

```bash
jupyter notebook --ip 0.0.0.0 --no-browser --allow-root
```







## Introduce Sonic Visualiser


## The physics of sound

## Overtones



## Introduce spectrograms


## Timbre
    - compare guitar and clarinet
    - compare to drums
    - compare male and female voices
    - compare applause and voice
