# Get script directory

```bash
dir=$(cd -P -- "$(dirname -- "$(realpath -- "$0")")" && pwd -P)
```

or just `cd` to it:

```bash
cd -P -- "$(dirname -- "$(realpath -- "$0")")"
```
