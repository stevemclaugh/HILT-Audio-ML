


## Speech to Text

```python
`wav_pathname="Alexander-Charles_27_NRA-26_Near-or-Random_Acts_Tucson-AZ_8-27-12.wav"

r = sr.Recognizer()
with sr.AudioFile(wav_pathname) as source:
audio = r.record(source)    # read the entire audio file

# recognize speech using Sphinx
try:
print(r.recognize_sphinx(audio))
except sr.UnknownValueError:
print("Sphinx could not understand audio")
except sr.RequestError as e:
print("Sphinx error; {0}".format(e))
```
`