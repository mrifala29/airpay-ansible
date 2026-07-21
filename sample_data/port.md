# Airpay Infrastructure - Port Registry

This document tracks all allocated ports across the infrastructure to avoid collisions.

## Cache Services
| Service | Default Port | Protocol | Notes |
| :--- | :--- | :--- | :--- |
| **Redis** | `6379` | TCP | Used for caching and pub/sub. Uses host network mode. |

## IAM Services
| Service | Default Port | Protocol | Notes |
| :--- | :--- | :--- | :--- |
| **Keycloak** | `8080` | TCP | Web UI and API endpoint. Uses host network mode. |
| **Keycloak DB (Postgres)** | `5432` | TCP | Internal DB for Keycloak. Uses host network mode. |

## Messaging Services
| Service | Default Port | Protocol | Notes |
| :--- | :--- | :--- | :--- |
| **RabbitMQ** | `5672` | TCP | AMQP Protocol. Uses host network mode. |
| **RabbitMQ UI** | `15672` | TCP | Management Web UI. Uses host network mode. |

## Observability Services
| Service | Default Port | Protocol | Notes |
| :--- | :--- | :--- | :--- |
| **Grafana** | `3000` | TCP | Metrics Dashboard Web UI. Uses host network mode. |

## Orchestration Services
| Service | Default Port | Protocol | Notes |
| :--- | :--- | :--- | :--- |
| **Temporal gRPC** | `7233` | TCP | Frontend service endpoint. Uses host network mode. |
| **Temporal UI** | `8088` | TCP | Web UI (Changed from 8080 to avoid Keycloak collision). |
| **Temporal DB (Postgres)**| `5433` | TCP | Internal DB (Changed from 5432 to avoid Keycloak DB collision). |

## Security Services
| Service | Default Port | Protocol | Notes |
| :--- | :--- | :--- | :--- |
| **Infisical** | `8089` | TCP | Web UI and API (Changed from 8080 to avoid Keycloak collision). |
| **Infisical DB (Postgres)**| `5434` | TCP | Internal DB (Changed from 5432 to avoid Keycloak DB collision). |

## Database Services
| Service | Default Port | Protocol | Notes |
| :--- | :--- | :--- | :--- |
| **Aerospike Service** | `3300` | TCP | Client access (Changed from 3000 to avoid Grafana collision). |
| **Aerospike Fabric** | `3301` | TCP | Inter-node cluster communication. |
| **Aerospike Heartbeat**| `3302` | UDP/TCP | Cluster heartbeat. |
| **Aerospike Info** | `3303` | TCP | Admin/Info port. |
| **ClickHouse HTTP** | `8123` | TCP | REST API and HTTP Interface. |
| **ClickHouse Native** | `9000` | TCP | Native TCP protocol (used by clickhouse-client). |
| **ScyllaDB CQL** | `9042` | TCP | Cassandra Query Language client port. |
| **ScyllaDB Thrift**| `9160` | TCP | Legacy client port. |
| **ScyllaDB Cluster**| `7000` | TCP | Inter-node cluster communication. |
| **ScyllaDB API** | `10000` | TCP | REST API port. |
| **Yugabyte Master RPC** | `7002` | TCP | Inter-node Master (Shifted from 7000 vs ScyllaDB). |
| **Yugabyte Master UI** | `7100` | TCP | Master Web UI. |
| **Yugabyte TServer RPC**| `9002` | TCP | Inter-node TServer (Shifted from 9000 vs ClickHouse). |
| **Yugabyte TServer UI** | `9100` | TCP | TServer Web UI. |
| **Yugabyte YSQL** | `5435` | TCP | PostgreSQL compatible interface (Shifted from 5433 vs Temporal). |
| **Yugabyte YCQL** | `9043` | TCP | Cassandra compatible interface (Shifted from 9042 vs ScyllaDB). |
