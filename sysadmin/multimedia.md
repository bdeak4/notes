# multimedia

## ffmpeg

### reduce video file size

```
$ ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
```