# programming

## code review

- [How to do a code review](https://google.github.io/eng-practices/review/reviewer/) `handbook`

## slicing

- [Scratch-made SVG Donut & Pie Charts in HTML5](https://heyoka.medium.com/scratch-made-svg-donut-pie-charts-in-html5-2c587e935d72) `article`
- [Inside the mind of a frontend developer: Hero section](https://ishadeed.com/article/inside-frontend-developer-mind-hero-section/) `article`

## git

- [Git from the inside out](https://codewords.recurse.com/issues/two/git-from-the-inside-out) `article` 
- [Curing A Case Of Git-UX](https://peppe.rs/posts/curing_a_case_of_git-UX/) `article`
- [Learn Git Branching](https://learngitbranching.js.org/) `interactive tutorial`
- [Git Explorer](https://gitexplorer.com/) `interactive tutorial`
- [Git Alias Open Pull Request on GitHub](https://salferrarello.com/git-alias-open-pull-request-github/) `article`

search repository code changes:

```
$ git log -S "query" -p --all
```

search specific files for changes:

```
$ git log -S "query" -p --all -- **/models/user*.py
```

search for regex instead of string:

```
$ git log -G "^# TODO" -p --all
```

search repository commit messages:

```
$ git log --grep "query" --all
```

leaderboards:

```
$ git shortlog -sn --all --no-merges
```

today's work:

```
$ git log --since=00:00:00 --all --no-merges --oneline --author=<email>
```

complex logs:

```
$ git log --graph --all --decorate --stat --date=iso
```
