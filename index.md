# Humanities Research with Sound: Introduction to Audio Machine Learning

### Instructor: Steve McLaughlin

## Class Modules

#### Day 1

- [1.1 Up and running with Docker](Day_1/1.1.md)
- [1.2 Visual listening](Day_1/1.2.md)
- [1.3 Understanding sound](Day_1/1.3.md)
    - [Slides](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_1/Day_1_Sound.pptx?raw=true)
- [1.4 Command line introduction with Bash](Day_1/1.4.md)
- [1.5 Exiftool and Bash file manipulation](Day_1/1.5.md)
- [1.6 Essential CLI audio tools](Day_1/1.6.md)
- [1.7 Python introduction](Day_1/1.7.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_1/1.7_Python_Introduction.ipynb)


#### Day 2

- [2.1 Machine learning and sound](Day_2/2.1.md)
    - [Slides](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_2/Day_2_ML.pptx?raw=true)
- [2.2 NBC chime search with ATTK](Day_2/2.2.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_2/2.2_Classify_and_Play_NBC_Chimes.ipynb)
- [2.3 Plotting frequency domain and MFCCs with Librosa](Day_2/2.3.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_2/2.3_Plotting_frequency_and_MFCCs_with_Librosa.ipynb)
- [2.4 Pitch detection](Day_2/2.4.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_2/2.4%20Pitch_detection_over_time.ipynb)
- [2.5 Extracting features and training a scikit-learn classifier](Day_2/2.5.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_2/2.5_Simple_KNN_Chime_Classifier.ipynb)
- [2.6 NBC overseas correspondent classifier pt. 1: Labeling and training](Day_2/2.8.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_2/2.6_NBC_Overseas_Correspondent_Classifier.ipynb)


#### Day 3

- [3.1 NBC overseas correspondent classifier pt. 2: Classifying with pyAudioAnalysis](Day_3/3.1.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_3/3.1_Train_and_classify_with_pyAudioAnalysis.ipynb)

- [3.2 Corpus building & web scraping](Day_3/3.2.md)

#### Day 4

- [4.1 Automatic speech recognition](Day_4/4.1.md)
    - [Slides](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_4/Day_4.pptx?raw=true)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_4/4.1%20Automatic%20Speech%20Recognition.ipynb)
- [4.2 Kaldi ASR transcript search](Day_4/4.2.md)
    - [Jupyter Notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_4/4.2_Kaldi_ASR_search.ipynb)
- [4.3 Automatic speaker diarization](Day_4/4.3.md)
    - [Jupyter notebook](https://github.com/stevemclaugh/HILT-Audio-ML/blob/master/Day_4/4.3_Automatic_speaker_diarization.ipynb)



## Handy Docker commands

View currently running docker containers:

```bash
docker ps -a
```

Close and delete all currently running Docker containers:

```bash
docker rm -f $(docker ps -aq)
```

### Download and launch Docker container

```bash
docker pull stevemclaugh/audio-ml-notebook

docker run -it --name audio_ml_notebook -p 8888:8888 -v ~/Desktop/sharedfolder:/home/sharedfolder stevemclaugh/audio-ml-notebook
```

You can view the Dockerfile we're using for this course [here](https://github.com/stevemclaugh/audio-ml-notebook/blob/master/Dockerfile).

A general introduction to Docker: [Docker for Beginners](https://prakhar.me/docker-curriculum/).


### Group notepad for sharing snippets & links

- [https://docs.google.com/document/d/1IXeOAQRcUsu5AH656BhnlXWoFgDZY168hhqjZ8BGbxI/edit?usp=sharing](https://docs.google.com/document/d/1IXeOAQRcUsu5AH656BhnlXWoFgDZY168hhqjZ8BGbxI/edit?usp=sharing)


## Software to Install Before Class

- Docker CE or Docker Toolbox
    - https://store.docker.com/search?type=edition&offering=community
    - https://www.docker.com/products/docker-toolbox

- Atom or Geany
    - https://atom.io
    - https://www.geany.org

- Sonic Visualiser
    - http://www.sonicvisualiser.org/download.html

- VLC Media Player
    - http://www.videolan.org/vlc/index.html

- OpenRefine
    - http://openrefine.org/download.html

- Praat (optional)
    - http://www.fon.hum.uva.nl/praat/

- OpenOffice (if you don't have a copy of Excel)
    - https://www.openoffice.org/download/


## Further reading

- [Command line setup steps for macOS](https://gist.github.com/stevemclaugh/7cdc925233995af27dc947b8903b7d10)

- [Guide to installing FFmpeg with mp3 support on macOS](https://gist.github.com/stevemclaugh/aa96cb5d8add3bfded51e0e586179959)

### Audio ML in archives

- [Speech Trax: Vocal Tracking of Famous French Speakers](http://recherche.ina.fr/eng/Details-projets/Speech-Trax), Vallet Carrive, Nabi, and Derval


### Python

- [*The Hitchhiker's Guide to Python*](http://shop.oreilly.com/product/0636920042921.do) by Kenneth Reitz and Tanya Schlusser

- [*Introduction to Machine Learning with Python*](http://shop.oreilly.com/product/0636920030515.do) by Andreas C. Müller and Sarah Guido (2016)


### Jupyter

- [“The Jupyter Notebook”](http://jupyter-notebook.readthedocs.io/en/latest/notebook.html)


### Audio

- [*Mathematics for the Nonmathematician*](https://www.amazon.com/Mathematics-Nonmathematician-Morris-Kline/dp/0486248232) by Morris Kline, chapters 18 and 19 (1985)

- [*Listening: An Introduction to the Perception of Auditory Events*](https://mitpress.mit.edu/books/listening) by Stephen Handel (1989)

- [*Principles of Digital Audio*, Sixth Edition](https://www.amazon.com/Principles-Digital-Audio-Sixth-Video/dp/0071663460) by Ken C. Pohlmann (2010)


### Stats & Machine Learning

- [Machine Learning](https://www.coursera.org/learn/machine-learning) on Coursera, taught by Andrew Ng

- [*Data Science from Scratch: First Principles with Python*](http://shop.oreilly.com/product/0636920033400.do) by Joel Grus (2015)

- [*An Introduction to Statistical Learning*](http://www-bcf.usc.edu/~gareth/ISL/) by Gareth James, Daniela Witten, Trevor Hastie, and Robert Tibshirani (2015)

- [*The Elements of Statistical Learning*](https://statweb.stanford.edu/~tibs/ElemStatLearn/) by Trevor Hastie, Robert Tibshirani, and Jerome Friedman (2009)
