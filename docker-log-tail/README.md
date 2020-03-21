## Requirements

* Vagrant
* vagrant-docker-compose

## 1. Run `vagrant up`

```bash
vagrant up
```

## 2. Run fluentd

```bash
vagrant ssh
cd /vagrant_data
docker-compose up
```

## 3. log event

```bash
vagrant ssh
cd /vagrant_data
docker run --rm bash:5 echo '{"message": "test", "level": "test", "timestamp": "2020-03-19T23:33:28+09:00"}'
```