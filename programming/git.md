# git

- [Curing A Case Of Git-UX](https://peppe.rs/posts/curing_a_case_of_git-UX/) `article`
- [Learn Git Branching](https://learngitbranching.js.org/) `interactive tutorial`
- [Git Alias Open Pull Request on GitHub](https://salferrarello.com/git-alias-open-pull-request-github/) `article`

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

### leaderboards

```
$ git shortlog -sn --all --no-merges
```

### today's work

```
$ git log --since=00:00:00 --all --no-merges --oneline --author=<email>
```

### complex logs

```
$ git log --graph --all --decorate --stat --date=iso
```