# `docker-compose` file collection
*Versi bahasa Indonesia: https://github.com/rochimfn/compose-collection#readme*

## About
A collection of `docker-compose` configurations for learning and development purposes

## Preparation
The entire `docker-compose.yaml` configuration uses a network share named `database`.

```bash
docker network create database
```

## Usage
Go to the service directory you want to run and execute `docker-compose`.

```bash
# Start the services
cd postgres
docker-compose up -d

# Tearing down the services
cd postgres
docker-compose down
```

## Service list

### `adminer`

* exposed ports: `8070`

### `db2 community edition`

* exposed ports: `50000`
* username: `db2inst1`
* password: `password`

### `debezium (with kafka)`

* connect
    * exposed ports: `8083`
* kafka
    * exposed ports: `9092`
* kafka-ui
    * exposed ports: `3300`
* zookeeper
    * exposed ports: `2181`
    * exposed ports: `2888`
    * exposed ports: `3888`

### `debezium-server with pulsar`

* debezium
    * exposed ports: `8080`
    * **set the configuration first !!!**: `conf/application.properties`
* pulsar
    * exposed ports: `6650`
    * exposed ports: `7080`
* pulsar-manager
    * exposed ports: `9527`
    * exposed ports: `7750`
    * **set up admin account first !!!**: [https://pulsar.apache.org/docs/en/administration-pulsar-manager/#set-administrator-account-and-password](https://pulsar.apache.org/docs/en/administration-pulsar-manager/#set-administrator-account-and-password)

### `elasticsearch & kibana`

* exposed ports(kibana): `5601`
* exposed ports(elasticsearch): `9200`, `9300`
* username: `elastic`
* password: `password`

### `hive`
* hiveserver2
    * exposed ports (hiveserver2): `10000`
    * exposed ports (hiveserver2 Web UI): `10002`
    * jdbc: `jdbc:hive2://localhost:10000/root`
    * beeline (docker): `docker exec -it hive-hiveserver2-1 beeline -u 'jdbc:hive2://localhost:10000/'`
    * beeline (eksternal): `beeline -u 'jdbc:hive2://localhost:10000/'`
* metastore
    * port diekspose: `9083`

### `julia`

* exposed ports: `8888`

### `mariadb`

* exposed ports: `3306`
* username: `root`
* password: `password`

### `mongo`

* exposed ports(client): `8081`
* exposed ports(server): `27017`
* username: `admin`
* password: `password`

### `mssql`

* exposed ports: `1433`
* username: `sa`
* password: `AEdCC.b9`

### `mysql`

* exposed ports: `3306`
* username: `root`
* password: `password`

### `neo4j`

* exposed ports(client): `7474`
* exposed ports(server): `7687`
* username: `neo4j`
* password: `password`

### `opendistro elasticsearch & kibana`

* exposed ports(kibana): `5601`
* exposed ports(elasticsearch): `9200`, `9600`
* username: `admin`
* password: `admin`

### `openldap`

* openldap
    * exposed ports: `389`
    * exposed ports: `636`
    * login admin: `cn=admin,dc=example,dc=org`
    * login readonly: `cn=readonly,dc=example,dc=org`
    * password: `password`
* phpLDAPadmin
    * exposed ports: `6443`


### `postgres`

* pgadmin
    * exposed ports: `8060`
    * email: `admin@local.dev`
    * password: `password`
* postgres
    * exposed ports: `5432`
    * username: `admin`
    * password: `password`

### `rabbitmq`

* exposed ports(client): `15672`
* exposed ports(server): `5672`
* username: `guest`
* password: `guest`

### `redis`

* redis
    * exposed ports: `6379`

### `redpanda`

* broker
    * exposed ports(schema-registry): `18081`
    * exposed ports(pandaproxy): `18082`
    * exposed ports(broker): `19092`
    * exposed ports(admin api): `19644`
* console
    * exposed ports: `8080`
* connect
    * exposed ports: `8083`

### `superset`

* superset
    * exposed ports: `8088`
    * manual provision (execute only at first up): 
    ```bash
    docker-compose exec superset superset fab create-admin \
                --username admin \
                --firstname Superset \
                --lastname Admin \
                --email admin@superset.com \
                --password admin

    docker-compose exec superset superset db upgrade

    # loading example (optional)
    docker-compose exec superset superset load_examples

    docker-compose exec superset superset init
    ```

### `tika`

* exposed ports: `9998`

### `zeppelin`

* exposed ports(server): `8080`
* exposed ports(spark): `4040`
