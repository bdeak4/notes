# shell commands

## networking

### find tcp ports device is listening on

```
# ss --listen --tcp --process --numeric
```

or more compact version:

```
# ss -ltpn
```

### find out which servers and devices are up and running

```
$ nmap -sP 192.168.<subnet>.0/24
```

### ping device on specific tcp port

```
$ nc -vz <ip> <port>
```

### ping device on specific udp port

```
$ nc -vzu <ip> <port>
```

## secrets

### Load environment variables from .env

```
export $(grep -v '^#' .env | xargs)
```

### Diff env files

```
diff <(cat .env.example | sed 's/=.*//g' | grep '^[A-Z]' | sort) <(cat .env | sed 's/=.*//g' | grep '^[A-Z]' | sort)
```

## ssh

### Force password auth

```sh
$ ssh -o PreferredAuthentications=password -o PubkeyAuthentication=no <user>@<host>
```
