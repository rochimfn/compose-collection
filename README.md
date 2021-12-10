# Koleksi `docker-compose`

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

### `elasticsearch & kibana`

* port diekspose(kibana): `5601`
* port diekspose(elasticsearch): `9200`, `9300`
* username: `elastic`
* password: `password`

### `debezium (with kafka)`

* zookeeper
    * port diekspose: `2181`
    * port diekspose: `2888`
    * port diekspose: `3888`
* kafka
    * port diekspose: `9092`
* connect
    * port diekspose: `8083`
* kafka-ui
    * port diekspose: `3300`
    

### `mariadb`

* port diekspose: `3306`
* username: `root`
* password: `password`

### `mongo`

* port diekspose(client): `8081`
* port diekspose(server): `27017`
* username: `admin`
* password: `password`

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

### `openldap`

* openldap
    * port diekspose: `389`
    * port diekspose: `636`
    * login admin: `cn=admin,dc=example,dc=org`
    * login readonly: `cn=readonly,dc=example,dc=org`
    * password: `password`
* phpLDAPadmin
    * port diekspose: `6443`


### `postgres`

* pgadmin
    * port diekspose: `8060`
    * email: `rochim@localhost`
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

### `zeppelin`

* port diekspose: `8080`
