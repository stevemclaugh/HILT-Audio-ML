




## Introduce Sonic Visualiser


## The physics of sound

## Overtones



## Introduce spectrograms


## Timbre
- compare guitar and clarinet
	- compare to drums
	- compare male and female voices
	- compare applause and voice



Convert all MP3s in a directory to mono 16/44.1 WAVs



```bash
`cd /path/to/directory

for file in *.mp3;
do ffmpeg -i $file -acodec pcm_s16le -ac 1 `basename "$file" .mp3`.wav;
done
```
`