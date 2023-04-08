# Fastest way to transfer files in local network

If you're on a local network, there's not much faster than:

source:

```
tar -cvf - /SOURCEDIR | nc TARGETIP 10240
```

target:

```
nc -l 10240 | tar -xvf -
```

Entirely unencrypted and unauthenticated, but there isn't likely to be anything faster. Should max out your disk IO easily.

[source](https://old.reddit.com/r/linuxadmin/comments/zu09e7/speed_up_rsync_or_use_tar_for_server/j1gl3i3/)
