# TIG stack (Telegraf + InfluxDB + Grafana) for Kontena environment
Kontena Stack for gathering and displaying metrics from nodes.

### Usage with Kontena
InfluxDB and Grafana needs instance scoped volumes to persist their data. Create the volumes:
```
kontena volume create --scope instance --driver local influxdb-data
kontena volume create --scope instance --driver local grafana-data
```
Install the stack:
```
kontena stack install
```

#### Additional information
Coming up..
