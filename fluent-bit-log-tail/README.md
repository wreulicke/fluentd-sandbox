## 1. Run fluentd

```bash
docker-compose up
```

## 2. log event

```bash
docker run bash:5 echo '{"message": "test", "timestamp": "2020-03-19T23:33:28+09:00"}'
```