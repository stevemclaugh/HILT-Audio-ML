Day 1, Session 1
9:30 – 10:45 am
Intro Remarks

My philosophy: play and screwing around is a good way to learn

Don't be discouraged. Think of it as a puzzle

Just Goole the error code. If you find yourself getting actually angry, like emotional -- just get up and make a cup of tea. Or come back to it tomorrow.




Day 1

What this course isn't
- a course on statistics
- a course on signal processing
- an course on programming/Python
- a course on state-of-the-art ML techniques

What this course focuses on
- finding, combining, and modifying existing tools
- understanding sound as data
  - the limits and possibilities of machine learning for sound collections




Advice at the outset
- Curb your expectations. Don't expect quick results.
- Frustration is natural. Push through it.




You don't need to understand every single last detail to do useful/interesting things

   But that means you need to be humble


Borrowing and stealing are ok
- both code and audio

It takes a little work every day over the course of years. 
- This is an introduction.


Giving you pristine notebooks is too mindless.


There's learning in copying and pasting.

I didn't make intentional mistakes, but I'm sure I made mistakes. When they come up, let's consider fixing the part of the learning process.





We have 20-some hours this week. If I can show you 20 tools in that time and give you some code you can take home and use for your own purposes, I think it'll be time well spent.



If I make a mistake, just pipe up and correct me. I've spent a lot of time working on this stuff, but I hesitate to call myself an expert. In the ideal case, I hope we can all learn from each other here.



The machine won't answer questions for you. It can suggest directions (help you sift), and it can help support arguments you're already making. 



Audio ML is really hard. And it can be really tedious. And it may or may not solve the kinds of problems you want to solve in your work.

Teaching an ML algorithm is like training a child ...
- This discussion includes audio quality: recordings on street, cassette dubs, etc.



But we're going to learn a lot of good stuff about how to think about sound and how to manage and manipulate collections of digital audio files.


Some of the things we're going to do this week are in a way pretty easy, even trivial. But ... baby steps. Everybody starts somewhere.



Install the following programs

Plaintext editor

- Atom: https://atom.io/
or
- Geany: https://www.geany.org/

Audio software

- Sonic Visualiser: http://www.sonicvisualiser.org/
- VLC Media Player: http://www.videolan.org/vlc/
- Praat (optional): http://www.fon.hum.uva.nl/praat/

Install Docker on Mac

- Docker Community Edition: https://store.docker.com/search?type=edition&offering=community

- Install Docker Toolbox (optional): https://www.docker.com/products/docker-toolbox


Install Docker on Windows

- Install Docker Toolbox: https://www.docker.com/products/docker-toolbox
- Double click "Docker Quickstart Terminal" on your desktop.


Install Cygwin (Windows only; optional)

- https://cygwin.com/install.html


If you don’t have Excel, you should install the OpenOffice ()(http://www.openoffice.org/download) suite, which includes a spreadsheet program called Calc. We won’t need it for today’s class.


Download and run Docker container


```bash
docker rm -f $(docker ps -aq)
```

Launch Docker container for this course:


```bash
mkdir ~/Desktop/sharedfolder

docker pull stevemclaugh/audio-ml-notebook

docker run -it --name audio_ml_notebook -p 8888:8888 -v ~/Desktop/sharedfolder:/home/sharedfolder stevemclaugh/audio-ml-notebook
```







Download and view audio

- Download audio with wget and view in Sonic Visualiser

```
wget ....zip
```






Audio bundle
- sine wave
  - clarinet recording
  - guitar
  - drum
  - speech recording
  - music recordings





Introduce Sonic Visualiser


The physics of sound

Overtones



Introduce spectrograms


Timbre
- compare guitar and clarinet
  - compare to drums
  - compare male and female voices
  - compare applause and voice



Convert all MP3s in a directory to mono 16/44.1 WAVs



```
cd /path/to/directory

for file in .mp3;
do ffmpeg -i $file -acodec pcms16le -ac 1 `basename "$file" .mp3`.wav;
done
```





Introduce Sonic Visualiser


The physics of sound

Overtones



Introduce spectrograms


Timbre
- compare guitar and clarinet
  - compare to drums
  - compare male and female voices
  - compare applause and voice


