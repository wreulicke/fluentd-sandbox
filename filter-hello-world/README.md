## 1. Run fluentd

```bash
docker run -ti --rm -p 8888:8888 -v $PWD:/fluentd/etc fluent/fluentd:v1.9-1 -c /fluentd/etc/fluentd.conf -v
```

## 2. log event for logout

```bash
curl -i -X POST -d 'json={"action":"logout","user":2}' http://localhost:8888/test.cycle
```

Not displayed in stdout for fluentd.

## 3. log event

```bash
curl -i -X POST -d 'json={"action":"login","user":2}' http://localhost:8888/test.cycle
```

Displayed in stdout for fluentd.