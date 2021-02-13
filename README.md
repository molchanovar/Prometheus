# Prometheus
SystemMonitor Prometheus+Grafana

### Мониторинг localhost 

Реализован мониторинг локального хоста на **Prometheus** (сбор метрик **node_exporter** + графики на **Grafana**)


Вывод графиков: загрузка CPU, использование RAM, показатели сети и свободное место на диске. 


Параметры графиков (на **PromQL**) в файле **Graphs**



### Быстрый старт Prometheus: 

Скачиваем prometheus / node_exporter / grafana
```
wget https://github.com/prometheus/prometheus/releases/download/v2.24.1/prometheus-2.24.1.linux-amd64.tar.gz
wget https://github.com/prometheus/node_exporter/releases/download/v1.1.0/node_exporter-1.1.0.linux-amd64.tar.gz
wget https://dl.grafana.com/oss/release/grafana-7.4.1.linux-amd64.tar.gz
```
Распаковываем: 
```
tar zxvf prometheus-*.linux-amd64.tar.gz 
tar zxvf node_exporter-*.linux-amd64.tar.gz 
tar zxvf grafana-*.linux-amd64.tar.gz
```
Запускаем `./prometheus --config.file=prometheus.yml` + `./node_exporter` + `./grafana-server`

Вариант #2 - Установка через добавление в репозиторий (Ubuntu)
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
