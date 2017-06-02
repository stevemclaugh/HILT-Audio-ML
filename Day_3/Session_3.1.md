# Day 3, Session 1
### 9:00 – 10:30 am	
## Lecture on the need to illuminate dark audio collections


<!-- mention BBC and INA -->



<!-- talk about my applause work -->


<!-- show wgbh labeler tool -->




## Speech to Text

<!-- Set this up as one way to illuminate archives -->


```python
wav*pathname="Alexander-Charles*27*NRA-26*Near-or-Random*Acts*Tucson-AZ*8-27-12.wav"

r = sr.Recognizer()
with sr.AudioFile(wav*pathname) as source:
audio = r.record(source)    # read the entire audio file

# recognize speech using Sphinx
try:
print(r.recognize*sphinx(audio))
except sr.UnknownValueError:
print("Sphinx could not understand audio")
except sr.RequestError as e:
print("Sphinx error; {0}".format(e))
```
