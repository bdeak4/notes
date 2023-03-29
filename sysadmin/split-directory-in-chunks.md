# Split directory in chunks

sometimes it can be useful to split directory with lot of files in smaller chunks

```
$ find -maxdepth 1 -type f -printf '%s\t%P\0' | sort -z -rn |
  (
      # x is max files per directory; d is directory number; k is file counter
      x=500 d=1 k=1
      while IFS=$'\t' read -r -d '' size path
      do
          printf "%d\t%d\t%s\n" $k $d "$path"    # File nr, Directory nr, Filename
          mkdir -p "../chunks/chunk-$d"
          mv -f "$path" "../chunks/chunk-$d/${path##*/}"

          [[ $((k++)) -ge $x ]] && { k=1; ((d++)); }    # Next directory
      done
  )
```

[source](https://unix.stackexchange.com/a/621946)
