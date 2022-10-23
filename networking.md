# networking

## device

### find tcp ports device is listening on

```
# ss --listen --tcp --process --numeric
```

or more compact version:

```
# ss -ltpn
```

## local

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
