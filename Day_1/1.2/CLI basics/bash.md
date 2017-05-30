```bash
`for file in *.mp3; do ffmpeg -i $file -acodec pcm_s16le -ac 1 `basename "$file" .mp3`.wav; done
````