# networking

- [The HTTP crash course nobody asked for](https://fasterthanli.me/articles/the-http-crash-course-nobody-asked-for) `article`

## shell commands

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

## wireguard

### Log connections

```
*/3 * * * * wg show all dump | grep 192.168.44 | awk 'BEGIN {}; {if (systime()-$6 <180 ) print strftime("\%m-\%d-\%Y \%H:\%M:\%S", systime()),$5, $4, (systime()-$6) "sec" } ; END {}' >> /var/log/wg.log
```

replace `192.168.44` with wireguard network prefix

## ssh

- [A Visual Guide to SSH Tunnels](https://iximiuz.com/en/posts/ssh-tunnels/) `article`

### remote session management

- [tmux](https://github.com/tmux/tmux)
- [dtach](https://github.com/crigler/dtach)

### kill session

"Enter" then ~ then . will kill a hung SSH connection, instead of having to close the terminal tab. 

### Force password auth

```
$ ssh -o PreferredAuthentications=password -o PubkeyAuthentication=no <user>@<host>
```
