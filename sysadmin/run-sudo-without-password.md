# Run sudo without password

```
$ echo "$USER ALL=(ALL:ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/$USER
```

[source](https://askubuntu.com/a/878705)
