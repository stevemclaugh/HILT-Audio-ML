# Day 1, Session 3
### 1:30 – 2:30 pm
## Sample-level audio manipulation

##### with credit due to https://zenodo.org/record/58336#.V-rh7pMrKRu (https://zenodo.org/record/58336#.V-rh7pMrKRu)


Open a new terminal window and download a WAV (or use one we grabbed before).

```bash
wget http://www.stephenmclaughlin.net/HILT/Day_1/Creeley-Robert_23_The-Warning_Chicago_5-15-61.wav
```

Create a new Jupyter notebook. In the first cell, let's import a few Python tools.

```
import librosa
import librosa.display
import IPython.display
import os
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.style as ms
ms.use('seaborn-muted')
%matplotlib inline
```

Now let's load our WAV as a Librosa object. 

```
wav_pathname = 'Creeley-Robert_23_The-Warning_Chicago_5-15-61.wav'

sample_array, sample_rate = librosa.load(wav_pathname)
```

We've just assigned two variables: `samples` is a numpy array of sample values; `sample_rate` is the sample rate, an integer. Print each of them and see what they look like.

By default, Librosa will resample the signal to 22050Hz. Alternatively, we can set the sample rate manually like so:

```
librosa.load(wav_pathname, sr=44100)
```

Or disable resampling to go with the original rate:

```
librosa.load(wav_pathname, sr=None)
```

Now let's flip it an reverse it. In Python, we can easily reverse the order of a list called `xyz` with the bracket notation `xyz[::-1]`.

```
librosa.output.write_wav('Reverse_Creeley_The-Warning_61.wav', sample_array[::-1], sample_rate)
```

Play the new file "Reverse_Creeley_The-Warning_61.wav" in an audio editor.


Now let's add some white noise to the original recording.

```
noise_array=[]

for sample in sample_array:
noise_array.append(((random.random()-0.5)*0.1)+sample)

noise_array = np.array(noise_array)

librosa.output.write_wav('Noisy_Creeley_The-Warning_61.wav', noise_array, sample_rate)
```






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
