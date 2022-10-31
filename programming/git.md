# git

## commands

### search repository code changes

```
$ git log -S "query" -p --all
```

search specific files:

```
$ git log -S "query" -p --all -- **/models/user*.py
```

search for regex instead of string:

```
$ git log -G "^# TODO" -p --all
```

### search repository commit messages

```
$ git log --grep "query" --all
```