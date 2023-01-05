# git

- [Git from the inside out](https://codewords.recurse.com/issues/two/git-from-the-inside-out) `article`
- [Git For Ages 4 And Up](https://www.youtube.com/watch?v=1ffBJ4sVUb4) `yt video`
- [Curing A Case Of Git-UX](https://peppe.rs/posts/curing_a_case_of_git-UX/) `article`
- [Learn Git Branching](https://learngitbranching.js.org/) `interactive tutorial`
- [Git Explorer](https://gitexplorer.com/) `interactive tutorial`
- [Git Alias Open Pull Request on GitHub](https://salferrarello.com/git-alias-open-pull-request-github/) `article`

complex logs

```
$ git log --graph --all --decorate --stat --date=iso
```

## search

search repository code changes (for regex search use `-G` instead of `-S`)

```
$ git log -S "query" -p --all
```

search specific files for changes

```
$ git log -S "query" -p --all -- **/models/user*.py
```

search commit messages

```
$ git log --grep "query" --all
```

## stats

leaderboards

```
$ git shortlog -sn --all --no-merges
```

today's work

```
$ git log --since=00:00:00 --all --no-merges --oneline --author=<email>
```



