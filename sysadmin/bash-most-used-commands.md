# Bash most used commands

```
$ history | awk '{$1="";print substr($0,2)}' | sort | uniq -c | sort -nr | head -n 10
```

[source](https://missing.csail.mit.edu/2020/command-line/#aliases-1)
