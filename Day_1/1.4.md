# Day 1, Session 4
### 2:45 – 4:30 pm
## Sample-level audio manipulation

##### with credit due to https://zenodo.org/record/58336#.V-rh7pMrKRu (https://zenodo.org/record/58336#.V-rh7pMrKRu)


Choose a WAV file to work with for the following exercise, or download one using the following command. A short recording of speech (such as a poetry reading) would be ideal.

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

Or disable resampling and use the original sample rate:

```
librosa.load(wav_pathname, sr=None)
```

Now let's flip it and reverse it. In Python, we can easily reverse the order of a list called `xyz` with the bracket notation `xyz[::-1]`.

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

For an added challenge, try mixing two recordings together.

## Plotting spectral frames and MFCCs

Open the notebook `1.3 Plotting Spectral Frames and MFCCs with Librosa`.

## Pitch detection

- [Aubio](https://aubio.org/manual/latest/)
- [Aubio pitch methods](https://aubio.org/manpages/latest/aubiopitch.1.html)

```
# Adapted from 
# https://github.com/aubio/aubio/blob/master/python/demos/demo_pitch.py

import sys
import numpy as np
from numpy import ma
from aubio import source, pitch
from matplotlib import pyplot as plt

%matplotlib inline

filename = "OSullivan-Maggie_10_Lottery-&-Requiem_States-of-Emergency_Rockdrill-11_05.mp3"


downsample = 1
samplerate = 44100 // downsample

win_s = 2048 // downsample # fft size
hop_s = 512  // downsample # hop size

s = source(filename, samplerate, hop_s)
samplerate = s.samplerate

tolerance = 0.8

pitch_o = pitch("yinfft", win_s, hop_s, samplerate)
pitch_o.set_unit("Hz")
pitch_o.set_tolerance(tolerance)

pitches = []
confidences = []

# total number of frames read
total_frames = 0
while True:
samples, read = s()
pitch = pitch_o(samples)[0]
#pitch = int(round(pitch))
confidence = pitch_o.get_confidence()
#print("%f %f %f" % (total_frames / float(samplerate), pitch, confidence))
pitches += [pitch]
confidences += [confidence]
total_frames += read
if read < hop_s: break

plt.figure(figsize=(100,5))
plt.plot(pitches)
plt.show()
```


```
pitches = np.array(pitches)
confidences = np.array(confidences)

cleaned_pitches = ma.masked_where(confidences < tolerance, pitches)
cleaned_pitches = ma.masked_where(cleaned_pitches > 1000, cleaned_pitches)

plt.figure(figsize=(100,5))
plt.plot(cleaned_pitches)
plt.show()
```

```
np.mean(cleaned_pitches)
```
## Histograms

```
def hist_polarity(text_in):
blob = TextBlob(sanitize(text_in))
sentiments=[sentence.sentiment.polarity for sentence in blob.sentences]
plt.figure(figsize=(20,10))
plt.hist(sentiments_smooth)

def hist_subjectivity(text_in):
blob = TextBlob(sanitize(text_in))
sentiments=[sentence.sentiment.subjectivity for sentence in blob.sentences]
plt.figure(figsize=(20,10))
plt.hist(sentiments)
```
