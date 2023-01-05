# scripting

## patterns

parse cli arguments:
```sh
while test $# -gt 0; do  
  case "$1" in  
    -a|--argument) shift; ARG="$1";;  
    -s|--switch) SWITCH=1;;
  esac  
  shift  
done
```

get script directory:
```sh
dir=$(cd -P -- "$(dirname -- "$0")" && pwd -P)
```