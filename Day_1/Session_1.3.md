# Day 1, Session 3
### 1:30 – 2:30 pm
## Sample-level audio manipulation

Extract samples & do FFT with LibRosa




- Exercise: reverse samples and write to new file

- Exercise: mix 2 sounds by adding their samples






## Speech to Text

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
