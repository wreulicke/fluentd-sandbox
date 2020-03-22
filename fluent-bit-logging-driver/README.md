## 1. Run fluentd

```bash
docker-compose up
```

## 2. log event

```bash
docker run --rm --log-driver=fluentd --log-opt fluentd-address=127.0.0.1:24224 bash:5 echo Hello Fluentd
```

> Note:
なぜか docker-composeからfluentd logging driverを指定すると使えないので
docker runで動かして動作確認