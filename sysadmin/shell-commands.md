# shell commands

## secrets

### Load environment variables from .env

```
export $(grep -v '^#' .env | xargs)
```

### Diff env files

```
diff <(cat .env.example | sed 's/=.*//g' | grep '^[A-Z]' | sort) <(cat .env | sed 's/=.*//g' | grep '^[A-Z]' | sort)
```

## cron jobs

- [Crontab guru](https://crontab.guru/) `tool`

## data parsing

- [jq](https://github.com/stedolan/jq) `json`
- [pup](https://github.com/EricChiang/pup) `html`
