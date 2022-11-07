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

- [A Visual Guide to SSH Tunnels](https://iximiuz.com/en/posts/ssh-tunnels/) `article`

### kill session

"Enter" then ~ then . will kill a hung SSH connection, instead of having to close the terminal tab. 

### Force password auth

```
$ ssh -o PreferredAuthentications=password -o PubkeyAuthentication=no <user>@<host>
```

## wireguard

### Log connections

```
*/3 * * * * wg show all dump | grep 192.168.44 | awk 'BEGIN {}; {if (systime()-$6 <180 ) print strftime("\%m-\%d-\%Y \%H:\%M:\%S", systime()),$5, $4, (systime()-$6) "sec" } ; END {}' >> /var/log/wg.log
```

replace `192.168.44` with wireguard network prefix

## cron jobs

- [Crontab guru](https://crontab.guru/) `tool`

### 

## multimedia

### reduce video file size

```
$ ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
```