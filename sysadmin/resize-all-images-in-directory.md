# Resize all images in directory

make sure you have [ImageMagick](https://www.imagemagick.org/script/download.php#unix) installed, then run:

```
$ find . -name '*.jpg' -or -name '*.png' -execdir mogrify -resize 1080x {} +
```
