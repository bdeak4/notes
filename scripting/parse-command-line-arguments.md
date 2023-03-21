# Parse command line arguments

```bash
while test $# -gt 0; do  
  case "$1" in  
    -a|--argument) shift; ARG="$1";;  
    -s|--switch) SWITCH=1;;
  esac  
  shift  
done
```
