## Create Spectrograms on CLI

```bash
`for f in *.mp3; do
basename=`basename $f .mp3`
ffmpeg -i """$f""" -f segment -segment_time 20 """$f""".%04d.wav ;
done
```
`

```bash
`for f in *.wav; do
basename=`basename $f .wav`
sox $f -n spectrogram -x 1600 -y 513 -r -o $basename.png;
done
```
`


