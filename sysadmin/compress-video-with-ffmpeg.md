# Compress video with ffmpeg

h264:

```
$ ffmpeg -i input.mp4 -vcodec h264 -acodec mp3 output.mp4
```

h265:

```
$ ffmpeg -i input.mp4 -vcodec libx265 -crf 18 -tag:v hvc1 -preset veryslow -acodec mp3 output.mp4
```
