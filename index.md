# Humanities Research with Sound: Introduction to Audio Machine Learning

### Instructor: Stephen McLaughlin

Libraries and archives have digitized thousands of hours of historical audio in recent years, including literary performances, radio programs, and oral histories. In the rush to preserve these recordings before their physical media decay, applying detailed metadata has often been an afterthought. Unlike digitized text, which is readily searchable in most cases, describing the contents of audio recordings typically means listening in real time. Using a range of tools, the High-Performance Sound Technologies for Access and Scholarship (HiPSTAS) project at the University of Texas at Austin has worked to shine a light on these large collections and encourage their use in research.

Participants will gain skills useful for using sound collections for a range of humanities research questions. By learning the basics of how to discover and identify patterns, search and sift collections of sounds, humanists can unlock new collections of valuable primary source material. This workshop will begin with an overview of machine learning techniques for expediting audio annotation, beginning with event detection classifiers, speaker diarization, and speech-to-text processing. We will then use the GUI-based tool Sonic Visualiser to tag audio events and use those data to search for additional instances in a wider corpus. We will train binary classifiers using pyAudioAnalysis, a wrapper for the Python machine learning library scikit-learn, and will conduct several batch processing steps using Audio Tagging Toolkit, developed by the HiPSTAS team.

Students should bring a laptop (any operating system) as well as headphones or earbuds. All tools used in this workshop are open source or free software. An audio corpus will be provided for the hands-on demo, but students should feel free to bring samples from collections they hope to explore. Experience recording or editing digital audio will be helpful but is not strictly necessary. No prior experience with Python or machine learning is required.

## Class Sessions

[Day 1, Session 1](Day_1/Session_1.1.md) | [Day 1, Session 2](Day_1/Session_1.2.md) | [Day 1, Session 3](Day_1/Session_1.3.md) | [Day 1, Session 4](Day_1/Session_1.4.md)
[Day 2, Session 1](Day_2/Session_2.1.md) | [Day 2, Session 2](Day_2/Session_2.2.md) | [Day 2, Session 3](Day_2/Session_2.3.md) | [Day 2, Session 4](Day_2/Session_2.4.md)
[Day 3, Session 1](Day_3/Session_3.1.md) | [Day 3, Session 2](Day_3/Session_3.2.md) | [Day 3, Session 3](Day_3/Session_3.3.md) | [Day 3, Session 4](Day_3/Session_3.4.md)
[Day 4, Session 1](Day_1/Session_4.1.md) | [Day 4, Session 2](Day_1/Session_4.2.md) | [Day 4, Session 3](Day_1/Session_4.3.md) | [Day 4, Session 4](Day_1/Session_4.4.md)

### Group notepad (for sharing links etc.)

- [https://etherpad.net/p/HILT-Audio-ML](https://etherpad.net/p/HILT-Audio-ML)


## Getting started with Docker


## Getting started with Docker


Here's a general overview of [Docker for beginners](https://prakhar.me/docker-curriculum/).

And here's a [cheat sheet](https://www.docker.com/sites/default/files/Docker_CheatSheet_08.09.2016_0.pdf) with basic Docker commands.

In case you're interested, here's a [handy overview](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/) of best practices for creating Docker containers.


View currently running docker containers:

```bash
docker ps -a
```

Close and delete all currently running Docker containers:

```bash
docker rm -f $(docker ps -aq)
```

Launch Docker container for this course:

```bash
mkdir ~/Desktop/sharedfolder

docker pull stevemclaugh/audio-ml-notebook

docker run -it --name audio*ml*container2 -p 8888:8888 -v ~/Desktop/sharedfolder:/home/sharedfolder stevemclaugh/audio-ml-notebook
```

You can view the Dockerfile we're using to build our container here ()(https://github.com/stevemclaugh/audio-ml-notebook/blob/master/Dockerfile).

## Running Python and other command-line tools on macOS

If you're using macOS, see the following guide on getting up and running with bash and Python:
- https://github.com/stevemclaugh/Python-Text-Workshop_Northwestern_2016/blob/Master/01_Pre-Workshop_OS-X.md


## Further Reading



### If you want more Python

Hitchhiker's Guide to Python

Introduction to Machine Learning with Python


### If you want more on Jupyter

-   “The Jupyter Notebook.” [http://jupyter-notebook.readthedocs.io/en/latest/notebook.html](http://jupyter-notebook.readthedocs.io/en/latest/notebook.html)



### If you want more on audio

Stephen Handel 1989 - Listening

Principles of Digital Audio


### If you want more stats

Data Science from Scratch

An Introduction to Statistical Learning 

The Elements of Statistical Learning 

The Coursera Machine Learning course 



### Podcasts

