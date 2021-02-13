**CPU% usage**
```
(((count(count(node_cpu_seconds_total{instance="localhost:9100",job="node-exporter"}) by (cpu))) - avg(sum by (mode)(irate(node_cpu_seconds_total{mode="idle",instance="localhost:9100",job="node-exporter"}[5m])))) * 100) /count(count(node_cpu_seconds_total{instance="localhost:9100",job="node-exporter"}) by (cpu))
```

**Memory usage**
```
100 - ((node_memory_MemAvailable_bytes{instance="localhost:9100",job="node-exporter"} * 100) / node_memory_MemTotal_bytes{instance="localhost:9100",job="node-exporter"})
```

**Disk Space Used**
```
node_filesystem_size_bytes{instance="localhost:9100",job="node-exporter",device!~'rootfs'} - node_filesystem_avail_bytes{instance="localhost:9100",job="node-exporter",device!~'rootfs'}
```

**Network**
```
irate(node_network_receive_bytes_total{instance="localhost:9100",job="node-exporter"}[5m])*8
irate(node_network_transmit_bytes_total{instance="localhost:9100",job="node-exporter"}[5m])*8
```
