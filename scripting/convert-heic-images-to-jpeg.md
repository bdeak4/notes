# Convert HEIC images to JPEG

```sh
for img in *.HEIC; do convert "$(basename $img .HEIC)"{.HEIC,.JPG}; done
```
