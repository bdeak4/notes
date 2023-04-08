# Unknown server investigation

who is logged in right now:

```
$ w
```

log in history:

```
$ last
```

running systemd services:

```
$ systemctl | grep running
```

running processes:

```
$ ps auxwf
```

opened ports and connections:

```
$ lsof -i -P
```

docker containers:

```
$ docker ps
```
