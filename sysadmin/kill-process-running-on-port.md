# Kill process running on port

```
kill -9 (lsof -nP -t -iTCP:8080 -sTCP:LISTEN)
```
