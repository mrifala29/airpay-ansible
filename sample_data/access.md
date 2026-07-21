# Service Access Information

This file contains access credentials, endpoints, and other access-related details for all services managed by Ansible.

## Cache Services

### Redis
- **Host**: (IP of `redis_nodes` from inventory)
- **Port**: `6379`
- **Default Password**: `redis_dev_password_123` (Configured in `inventories/dev/group_vars/cache.yml`)
- **Connection Test**: `redis-cli -h <IP> -p 6379 -a redis_dev_password_123 ping`

## IAM Services

### Keycloak
- **Host**: (IP of `keycloak_nodes` from inventory)
- **Port**: `8080`
- **Admin User**: `admin`
- **Admin Password**: `kc_dev_password_123` (Configured in `inventories/dev/group_vars/iam.yml`)
- **Web UI**: `http://<IP>:8080`

## Messaging Services

### RabbitMQ
- **Host**: (IP of `rabbitmq_nodes` from inventory)
- **AMQP Port**: `5672`
- **Web UI**: `http://<IP>:15672`
- **User**: `admin`
- **Password**: `rmq_dev_password_123` (Configured in `inventories/dev/group_vars/messaging.yml`)

## Observability Services

### Grafana
- **Host**: (IP of `grafana_nodes` from inventory)
- **Web UI**: `http://<IP>:3000`
- **User**: `admin`
- **Password**: `grafana_dev_password_123` (Configured in `inventories/dev/group_vars/observability.yml`)

## Orchestration Services

### Temporal
- **Host**: (IP of `temporal_nodes` from inventory)
- **gRPC Port**: `7233`
- **Web UI**: `http://<IP>:8088`
- **Internal DB Password**: `temporal_db_dev_password` (Configured in `inventories/dev/group_vars/orchestration.yml`)

## Security Services

### Infisical
- **Host**: (IP of `infisical_nodes` from inventory)
- **Web UI**: `http://<IP>:8089`
- **Internal DB Password**: `infisical_db_dev_password`
- **Keys**: Must configure `infisical_auth_secret` and `infisical_encryption_key` in `inventories/dev/group_vars/security.yml`

## Database Services

### Aerospike
- **Host**: (IP of `aerospike_nodes` from inventory)
- **Client Port**: `3300`
- **Connection Test**: `aql -h <IP> -p 3300`

### ClickHouse
- **Host**: (IP of `clickhouse_nodes` from inventory)
- **HTTP Port**: `8123`
- **TCP Port**: `9000`
- **User**: `default`
- **Password**: `ch_dev_password_123` (Configured in `inventories/dev/group_vars/databases.yml`)
- **Connection Test**: `clickhouse-client --host <IP> --port 9000 --password ch_dev_password_123`

### ScyllaDB
- **Host**: (IP of `scylladb_nodes` from inventory)
- **CQL Port**: `9042`
- **Cluster Name**: `airpay-scylla-cluster-dev` (Configured in `inventories/dev/group_vars/databases.yml`)
- **Connection Test**: `cqlsh <IP> 9042`

### YugabyteDB
- **Host**: (IP of `yugabytedb_nodes` from inventory)
- **Master UI**: `http://<IP>:7100`
- **TServer UI**: `http://<IP>:9100`
- **YSQL Port (Postgres)**: `5435` (Test: `ysqlsh -h <IP> -p 5435 -U yugabyte`)
- **YCQL Port (Cassandra)**: `9043` (Test: `ycqlsh <IP> 9043`)
- **Credentials**: Defaults to user `yugabyte` with no password out of the box for dev.
