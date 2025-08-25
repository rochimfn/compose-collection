# Koleksi `docker-compose`
*English version: https://github.com/rochimfn/compose-collection/blob/main/README.en.md*

## Tentang
Koleksi konfigurasi docker-compose untuk keperluan belajar dan pengembangan.

## Persiapan
Seluruh konfigurasi `docker-compose.yaml` menggunakan jaringan berbagi dengan nama `database`.

```bash
docker network create database
```

## Penggunaan
Masuk ke direktori compose yang ingin dijalankan lalu jalankan `docker-compose`.

```bash
# Contoh untuk menjalankan
cd postgres
docker-compose up -d

# Contoh untuk mematikan
cd postgres
docker-compose down
```

## Daftar layanan

### `adminer`

* port diekspose: `8070`

### `cassandra`

* cassandra
    * port diekspose: `9042`

### `db2 community edition`

* port diekspose: `50000`
* username: `db2inst1`
* password: `password`

### `debezium (with kafka)`

* connect
    * port diekspose: `8083`
* kafka
    * port diekspose: `9092`
* kafka-ui
    * port diekspose: `3300`
* zookeeper
    * port diekspose: `2181`
    * port diekspose: `2888`
    * port diekspose: `3888`

### `debezium-server with pulsar`

* debezium
    * port diekspose: `8080`
    * **atur konfigurasi dulu !!!**: `conf/application.properties`
* pulsar
    * port diekspose: `6650`
    * port diekspose: `7080`
* pulsar-manager
    * port diekspose: `9527`
    * port diekspose: `7750`
    * **atur akun admin dulu !!!**: [https://pulsar.apache.org/docs/en/administration-pulsar-manager/#set-administrator-account-and-password](https://pulsar.apache.org/docs/en/administration-pulsar-manager/#set-administrator-account-and-password)

### `elasticsearch & kibana`

* port diekspose(kibana): `5601`
* port diekspose(elasticsearch): `9200`, `9300`
* username: `elastic`
* password: `password`

### `hive`

* hiveserver2
    * port diekspose (hiveserver2): `10000`
    * port diekspose (hiveserver2 Web UI): `10002`
    * jdbc: `jdbc:hive2://localhost:10000/root`
    * beeline (docker): `docker exec -it hive-hiveserver2-1 beeline -u 'jdbc:hive2://localhost:10000/'`
    * beeline (eksternal): `beeline -u 'jdbc:hive2://localhost:10000/'`
* metastore
    * port diekspose: `9083`

### `impala`

* port diekspose (Beeswax): `21000`
* port diekspose (HiveServer2): `21050` 
* port diekspose (Impala debug Web UI): `25000` 
* port diekspose (StateStore debug Web UI): `25010` 
* port diekspose (Catalog Server debug Web UI): `25020`

### `influxdb`

* port diekspose: `8086`
* username: `influx`
* password: `password`

### `julia`

* port diekspose: `8888`

### `livebook`

* port diekspose (Web UI): `8080`
* port diekspose: `8081`

### `mariadb`

* port diekspose: `3306`
* username: `root`
* password: `password`

### `mongo`

* port diekspose(client): `8081`
* port diekspose(server): `27017`
* username: `admin`
* password: `password`

### `mosquitto`

* port diekspose: `1883`, `9001`

### `mssql`

* port diekspose: `1433`
* username: `sa`
* password: `AEdCC.b9`

### `mysql`

* port diekspose: `3306`
* username: `root`
* password: `password`

### `neo4j`

* port diekspose(client): `7474`
* port diekspose(server): `7687`
* username: `neo4j`
* password: `password`

### `opendistro elasticsearch & kibana`

* port diekspose(kibana): `5601`
* port diekspose(elasticsearch): `9200`, `9600`
* username: `admin`
* password: `admin`

### `openldap`

* openldap
    * port diekspose: `389`
    * port diekspose: `636`
    * login admin: `cn=admin,dc=example,dc=org`
    * login readonly: `cn=readonly,dc=example,dc=org`
    * password: `password`
* phpLDAPadmin
    * port diekspose: `6443`

### `oracle`

* port diekspose: `1521`
* username: `SYS`, `SYSTEM` dan `PDBADMIN`
* password: `password`

### `pgvector`

* port diekspose: `5431`
* username: `admin`
* password: `password`
* database: `postgres`

### `postgres`

* pgadmin
    * port diekspose: `8060`
    * email: `admin@local.dev`
    * password: `password`
* postgres
    * port diekspose: `5432`
    * username: `admin`
    * password: `password`

### `rabbitmq`

* port diekspose(client): `15672`
* port diekspose(server): `5672`
* username: `guest`
* password: `guest`

### `redis`

* redis
    * port diekspose: `6379`

### `redpanda`

* broker
    * port diekspose(schema-registry): `18081`
    * port diekspose(pandaproxy): `18082`
    * port diekspose(broker): `19092`
    * port diekspose(admin api): `19644`
* console
    * port diekspose: `8080`
* connect
    * port diekspose: `8083`

### `scylla`

* scylla
    * port diekspose: `9042`

### `superset`

* superset
    * port diekspose: `8088`
    * manual provision: 
    ```bash
    docker-compose exec superset superset fab create-admin \
                --username admin \
                --firstname Superset \
                --lastname Admin \
                --email admin@superset.com \
                --password admin

    docker-compose exec superset superset db upgrade

    docker-compose exec superset superset load_examples

    docker-compose exec superset superset init
    ```

### `tika`

* port diekspose: `9998`

### `timescaledb`

* port diekspose: `5432`
* username: `postgres`
* password: `password`

### `zeppelin`

* port diekspose(server): `8080`
* port diekspose(spark): `4040`
