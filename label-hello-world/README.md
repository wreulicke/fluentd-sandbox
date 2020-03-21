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

## Note

https://docs.fluentd.org/quickstart/life-of-a-fluentd-event

> The new configuration contains a @label key on the source indicating that any further steps takes place on the STAGING Label section. The expectation is that every Event reported on the Source, the Routing engine will continue processing on STAGING, for hence it will skip the old filter definition.
