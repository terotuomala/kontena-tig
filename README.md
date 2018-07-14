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

### Additional information
- Database `telegraf` will be created to InfluxDB
- InfluxDB users `admin`, `grafana` (read permissions) and `telegraf` (read and write permissions) will be created and their passwords will be stored to Kontena Vault.
- Telegraf agent authenticates to InfluxDB using `telegraf` user.
- Grafana user `admin` will be created and it's password will be stored to Kontena Vault.
- Datasource (InfluxDB) for Grafana will be created using `grafana` user.
- Dashboard for Grafana displaying docker-engine metrics from nodes will be created.
