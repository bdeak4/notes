# Speed up video with ffmpeg

speed up 60 fps video 10x:

```
ffmpeg -i input.mp4 -filter:v "setpts=PTS/10,fps=60" -an output.mp4
```

source: <https://superuser.com/a/1782682>
