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
- Database `telegraf` will be created to InfluxDB
- InfluxDB users `admin` and `telegraf` will be created and their passwords will be stored to Kontena Vault.
- Grafana user `admin` will be created and it's password will be stored to Kontena Vault.
- Datasource (InfluxDB) for Grafana and dashboard displaying docker metrics from nodes will be created. 
