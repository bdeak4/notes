# Convert images to webp recursively

```
find . -name "*.png" -or -name '*.jpg' -or -name '*.jpeg' | parallel -eta cwebp {} -o {.}.webp
```
