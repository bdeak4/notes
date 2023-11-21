# Compress video with ffmpeg

h264:

```
$ ffmpeg -i input.mp4 -vcodec h264 -acodec mp3 output.mp4
```

h265:

```
$ ffmpeg -i input.mp4 -vcodec libx265 -crf 28 -acodec mp3 output.mp4
```
