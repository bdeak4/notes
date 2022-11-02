# git

- [Curing A Case Of Git-UX](https://peppe.rs/posts/curing_a_case_of_git-UX/) `article`

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