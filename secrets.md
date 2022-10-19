# secrets

## Load environment variables from .env

```
export $(grep -v '^#' .env | xargs)
```

## Diff env files

```
diff <(cat .env.example | sed 's/=.*//g' | grep '^[A-Z]' | sort) <(cat .env | sed 's/=.*//g' | grep '^[A-Z]' | sort)
```
