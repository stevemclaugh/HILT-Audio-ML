# Humanities Research with Sound: Introduction to Audio Machine Learning

### Instructor: Stephen Reid McLaughlin

## Class Modules

- [1.1 Intro and setup](Day_1/1.1.md)
- [1.2 Visual listening](Day_1/1.2.md)
- [1.3 Understanding sound](Day_1/1.3.md)
- [1.4 CLI intro with Bash](Day_1/1.4.md)
- [1.5 Exiftool and Bash file manipulation](Day_1/1.5.md)
- [1.6 CLI audio essentials](Day_1/1.6.md)
- [1.7 Python introduction](Day_1/1.7.md)
- [1.8 Plotting spectral data and MFCCs with Librosa](Day_1/1.8.md)

### Group notepad (for sharing links etc.)

- [https://etherpad.net/p/HILT-Audio-ML](https://etherpad.net/p/HILT-Audio-ML)


## Install the following programs before class


- Docker CE or Docker Toolbox (Either version is fine; I had some difficulty installing Docker CE on Windows.)
    https://store.docker.com/search?type=edition&offering=community
    https://www.docker.com/products/docker-toolbox

- Atom or Geany (or whatever plaintext editor you prefer)
    https://atom.io
    https://www.geany.org/

- Sonic Visualiser
    http://www.sonicvisualiser.org/download.html

- VLC Media Player
    http://www.videolan.org/vlc/index.html

- OpenRefine
    http://openrefine.org/download.html

- Praat (optional)
    http://www.fon.hum.uva.nl/praat/

- OpenOffice (if you don't have a copy of Excel)
    https://www.openoffice.org/download/


## Handy Docker commands

View currently running docker containers:

```bash
docker ps -a
```

Close and delete all currently running Docker containers:

```bash
docker rm -f $(docker ps -aq)
```

### Steps to launch Docker container

```bash
docker pull stevemclaugh/audio-ml-notebook

docker run -it --name audio_ml_notebook -p 8888:8888 -v ~/Desktop/sharedfolder:/home/sharedfolder stevemclaugh/audio-ml-notebook
```

You can view the Dockerfile we're using to build our container [here](https://github.com/stevemclaugh/audio-ml-notebook/blob/master/Dockerfile).

A general introduction to Docker: [Docker for Beginners](https://prakhar.me/docker-curriculum/).

In case you're interested, here's a [handy overview](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/) of best practices for creating Docker containers.



## Further reading

### Python

- [*The Hitchhiker's Guide to Python*](http://shop.oreilly.com/product/0636920042921.do) by Kenneth Reitz and Tanya Schlusser

- [*Introduction to Machine Learning with Python*](http://shop.oreilly.com/product/0636920030515.do) by Andreas C. Müller and Sarah Guido (2016)


### Jupyter

- [“The Jupyter Notebook”](http://jupyter-notebook.readthedocs.io/en/latest/notebook.html]


### Audio

- [*Listening: An Introduction to the Perception of Auditory Events*](https://mitpress.mit.edu/books/listening) by Stephen Handel (1989)

- [Principles of Digital Audio, Sixth Edition](https://www.amazon.com/Principles-Digital-Audio-Sixth-Video/dp/0071663460) by Ken C. Pohlmann (2010)


### Stats & Machine Learning

- [Machine Learning Coursera course](https://www.coursera.org/learn/machine-learning), taught by Andrew Ng


- [*Data Science from Scratch: First Principles with Python*](http://shop.oreilly.com/product/0636920033400.do) by Joel Grus (2015)

- [*An Introduction to Statistical Learning*](http://www-bcf.usc.edu/~gareth/ISL/) by Gareth James, Daniela Witten, Trevor Hastie, and Robert Tibshirani (2015)

- [*The Elements of Statistical Learning*](https://statweb.stanford.edu/~tibs/ElemStatLearn/)by Trevor Hastie, Robert Tibshirani, and Jerome Friedman (2009)
