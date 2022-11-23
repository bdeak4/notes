# programming

## code review

- [How to do a code review](https://google.github.io/eng-practices/review/reviewer/) `handbook`

## slicing

- [Scratch-made SVG Donut & Pie Charts in HTML5](https://heyoka.medium.com/scratch-made-svg-donut-pie-charts-in-html5-2c587e935d72) `article`
- [Inside the mind of a frontend developer: Hero section](https://ishadeed.com/article/inside-frontend-developer-mind-hero-section/) `article`
- [getElementsBySelector() (2003)](https://simonwillison.net/2003/Mar/25/getElementsBySelector/) `article`
- [Tree views in CSS](https://iamkate.com/code/tree-views/) `article`
- [A star rating widget in CSS](https://iamkate.com/code/star-rating-widget/) `article`

## functional programming

- [An introduction to functional programming](https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming) `article`

## git

- [Git from the inside out](https://codewords.recurse.com/issues/two/git-from-the-inside-out) `article`
- [Git For Ages 4 And Up](https://www.youtube.com/watch?v=1ffBJ4sVUb4) `yt video`
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