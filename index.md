# Humanities Research with Sound: Introduction to Audio Machine Learning

### Instructor: Stephen McLaughlin

Libraries and archives have digitized thousands of hours of historical audio in recent years, including literary performances, radio programs, and oral histories. In the rush to preserve these recordings before their physical media decay, applying detailed metadata has often been an afterthought. Unlike digitized text, which is readily searchable in most cases, describing the contents of audio recordings typically means listening in real time. Using a range of tools, the High-Performance Sound Technologies for Access and Scholarship (HiPSTAS) project at the University of Texas at Austin has worked to shine a light on these large collections and encourage their use in research.

Participants will gain skills useful for using sound collections for a range of humanities research questions. By learning the basics of how to discover and identify patterns, search and sift collections of sounds, humanists can unlock new collections of valuable primary source material. This workshop will begin with an overview of machine learning techniques for expediting audio annotation, beginning with event detection classifiers, speaker diarization, and speech-to-text processing. We will then use the GUI-based tool Sonic Visualiser to tag audio events and use those data to search for additional instances in a wider corpus. We will train binary classifiers using pyAudioAnalysis, a wrapper for the Python machine learning library scikit-learn, and will conduct several batch processing steps using Audio Tagging Toolkit, developed by the HiPSTAS team.

Students should bring a laptop (any operating system) as well as headphones or earbuds. All tools used in this workshop are open source or free software. An audio corpus will be provided for the hands-on demo, but students should feel free to bring samples from collections they hope to explore. Experience recording or editing digital audio will be helpful but is not strictly necessary. No prior experience with Python or machine learning is required.


## Getting started with Docker

In case you're interested, here's a [nice overview](https://www.digitalocean.com/community/tutorials/docker-explained-using-dockerfiles-to-automate-building-of-images) of Docker syntax.

And here's a [cheat sheet](https://www.docker.com/sites/default/files/Docker_CheatSheet_08.09.2016_0.pdf) with basic Docker commands.


```
mkdir ~/Desktop/sharedfolder

cd /path/to/Dockers

docker build -t audioml ./

docker run -it --name audio_ml_container -p 8888:8888 -v ~/Desktop/sharedfolder:/home/sharedfolder audioml
```
