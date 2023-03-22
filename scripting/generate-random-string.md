# Generate random string

```
str=$(tr -dc A-Za-z0-9 < /dev/urandom | head -c 13)
```

where 13 is length of generated string

[src](https://unix.stackexchange.com/a/230676)
