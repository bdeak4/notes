# Count number of files in each directory

```
du -a | sed '/.*\.\/.*\/.*/!d' | cut -d/ -f2 | sort | uniq -c | sort -nr
```
