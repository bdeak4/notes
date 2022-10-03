# networking

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
