## Basic SmacPy classifier



```
`for f in *.wav; do
ffmpeg -f u16le -ar 44100 -ac 1 -i $f 44s/$f ;
done

from smacpy import Smacpy

model = Smacpy("wavs/training", {'/Users/mclaugh/Dropbox/NBC_Chime_Search/chimes/CBD-440606_NBC0300-NewsandMusic_v2.wav':'chime', '/Users/mclaugh/Dropbox/NBC_Chime_Search/chimes/CBD-440606_NBC0700-News_Marker 01 Copy_v2.wav':'chime', '/Users/mclaugh/Dropbox/NBC_Chime_Search/chimes/CBD-440606_NBC1515-MusicandNews_v2.wav':'chime', '/Users/mclaugh/Dropbox/NBC_Chime_Search/chimes/CBD-440607_NBC0845-ModernRomances_v2.wav':'chime','/Users/mclaugh/Dropbox/NBC_Chime_Search/notchimes/CBD-440607_NBC1030-Helpmate_start_398.0_dur_3.0_class_0.0.wav':'not_chime', '/Users/mclaugh/Dropbox/NBC_Chime_Search/notchimes/CBD-440607_NBC1030-Helpmate_start_642.87_dur_3.0_class_0.0.wav':'not_chime', '/Users/mclaugh/Dropbox/NBC_Chime_Search/notchimes/CBD-440607_NBC1145-DavidHarum_newsinterruption_start_26.1_dur_3.0_class_0.0.wav':'not_chime', '/Users/mclaugh/Dropbox/NBC_Chime_Search/notchimes/CBD-440607_NBC1145-DavidHarum_newsinterruption_start_372.65_dur_3.0_class_0.0.wav':'not_chime'})

model.classify('wavs/testing/hubert01.wav')
```
`