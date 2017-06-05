# Day 2, Session 2
### 10:45 am – 12:00 pm

## Simple KNN Chime Classifier
#### ((As a group))


Move the following 4 directories to `sharedfolder`, then examine a few files from each set in Sonic Visualiser.

> NBC_Chimes
> NBC_Chimes_test
> NBC_Not_Chimes
> NBC_Not_Chimes_test

Now open the notebook `1.4 Simple KNN Chime Classifier`.

When we're finished with this unit, try swapping in some other scikit-learn classifiers.



### Training Classifier with pyAudioAnalysis
<!-- ((As a group)) -->

- Enter the following command in the terminal to launch the Python shell:

```
python
```

- Now enter the following to import packages and set ourworking directory to the desktop.

```python
from pyAudioAnalysis import audioTrainTest as aT
import os
os.chdir(os.path.expanduser('~/Desktop/'))
```

- If the desktop contains directories called "NBC*Chimes" and "NBC*Not*Chimes," the following command will use any WAV audio files they contain to train a support vector machine (SVM) classifier. *Note: You may have to press return twice when entering this command.*

```python
aT.featureAndTrain('NBC*Not*Chimes','NBC*Chimes' (), 1.0, 1.0, aT.shortTermWindow, aT.shortTermStep, "svm", "audio-ml-introduction-master/model/svm*chimes", False)
```

- This will output a model file called "svm*chimes" in the "model" directory within the audio-ml-introduction-master directory, along with two supporting files.

! ()(img/img06.png)

### Classifying Audio

- Open a new terminal window and enter the following commands to launch the included Jupyter notebook.

```
cd ~/Desktop/audio-ml-introduction-master/
jupyter notebook "02 Find and Play NBC Chimes.ipynb"
```

### Testing other models with pyAudioAnalysis


```
import os
os.chdir(os.path.expanduser('~/Desktop'))

from pyAudioAnalysis import audioTrainTest as aT

aT.featureAndTrain(['path/to/notchimes/','path/to/chimes/'], 1.0, 1.0, aT.shortTermWindow, aT.shortTermStep, "svm", "svm_model_name", False)
```


### Classifier options in pyAudioAnalysis

> svm
> knn
> gradientboosting
> extratrees
> randomforest



Example of Unsupervised


Demo code in Jupyter,

then batch with ATTK


