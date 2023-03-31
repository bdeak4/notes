# Add key to ssh-agent if not already added

```
$ ssh-add -L | grep -f ~/.ssh/key.pub >/dev/null || ssh-add ~/.ssh/key
```
