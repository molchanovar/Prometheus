# Prometheus
SystemMonitor Prometheus+Grafana

Быстрый старт Prometheus: 
```
wget https://github.com/prometheus/prometheus/releases/download/v2.24.1/prometheus-2.24.1.linux-amd64.tar.gz
tar xvfz prometheus-*.tar.gz
./prometheus --config.file=prometheus.yml
```
Для снятия мониторинга с хоста используется **node_exporter-1.1.0.linux-amd64**
```
wget https://github.com/prometheus/node_exporter/releases/download/v1.1.0/node_exporter-1.1.0.linux-amd64.tar.gz
tar xvfz node_exporter-*.*-amd64.tar.gz
cd node_exporter-*.*-amd64
./node_exporter
```

Дашборды выводятся через Grafana (добавить репозиторий и скачать версию OpenSource)
```
sudo vim /etc/yum.repos.d/grafana.repo

[grafana]
name=grafana
baseurl=https://packages.grafana.com/oss/rpm
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://packages.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
```
Установить `yum isntall grafana` и запустить sudo `systemctl start grafana-server`
