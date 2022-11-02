# writing scripts

## examples

### parse cli arguments

```sh
while test $# -gt 0; do  
  case "$1" in  
    -f|--flag) shift; FLAG="$1";;  
  esac  
  shift  
done
```

## script naming

without `.sh` extension when script is in some directory that is in `$PATH`
(like `/usr/bin`) and with `.sh` extension when in any directory not in `$PATH`

## resources

- [Unix shell script tactics](https://github.com/SixArm/unix-shell-script-tactics) `style guide`
- [Google Shell Style Guide](https://google.github.io/styleguide/shellguide.html) `style guide`
- [pure sh bible](https://github.com/dylanaraps/pure-sh-bible) `handbook`
- [shellcheck](https://www.shellcheck.net/) `tool`
