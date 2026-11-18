# I'm Rishabh Saraswat, an Open Source Contributions at Apache Cassandra, Apache Software Foundation

## ✅ Merged

- **Implemented Guardrail for Unprepared Statements** — Developed a new Guardrail configuration to detect, warn, or reject queries that bypass the prepared statement cache (cache misses).
  [Commit](https://github.com/apache/cassandra/commit/eabd2a27f5555a50cba6dc8b74d1f246a91081c0)

- **Add Sanitizing of Client Key-Value Pair Options in Driver Handshake** — Added sanitization of invalid values sent by driver in initial handshake.
  [Commit](https://github.com/apache/cassandra/commit/5f11d4bd5c27b1b9c711efb43fc15dda6b643065)

- **Security: TLS 1.3 & Perfect Forward Secrecy** — Resolved TLS 1.3 connectivity issues in cassandra-stress; implemented Perfect Forward Secrecy via updated cipher suites to meet modern encryption standards.
  [Commit](https://github.com/apache/cassandra/commit/9d89b47c68a6b476135c04b633e7d080a8ebe65f)

- **Testing Infrastructure: Blocked Data Simulation** — Engineered a simulation script for "blocked" data scenarios; verified storage utility accuracy for file sizes and date formats, optimizing disk-space diagnostics.
  [Commit](https://github.com/apache/cassandra/commit/6bf598dcdec8cc81a870fc5363308022bf11aead)

---

## 🔄 Under Review / In Progress

- **Cassandra Enhancement Proposal – 59** *(In Progress)* — Implementing in-band connection draining to enable graceful client disconnection during rolling maintenance and reduce ReadTimeouts in multi-node clusters.
  [PR #4953](https://github.com/apache/cassandra/pull/4953)

- **QoS Dispatching Technique for Cassandra** *(In Review)* — Developed a new configuration that allows users to choose a QoS servicing mechanism, giving ~26% faster reads and +16.8% more throughput.
  [PR #5195](https://github.com/apache/cassandra/pull/5195)

- **Driver Authentication Timeout Config** *(In Review)* — Developed a new configuration that sets a hard limit for clients to authenticate themselves, dropping the connection if the client doesn't authenticate.
  [PR #5261](https://github.com/apache/cassandra/pull/5261)
---
## 🛠 Tech Stack 
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white) ![Spring WebFlux](https://img.shields.io/badge/Spring_WebFlux-6DB33F?style=flat-square&logo=spring&logoColor=white) ![Project Reactor](https://img.shields.io/badge/Project_Reactor-6DB33F?style=flat-square&logo=spring&logoColor=white) ![gRPC](https://img.shields.io/badge/gRPC-244c5a?style=flat-square&logo=grpc&logoColor=white)
![Netty](https://img.shields.io/badge/Netty-000000?style=flat-square&logo=netty&logoColor=white) ![Lettuce](https://img.shields.io/badge/Lettuce-6DB33F?style=flat-square&logo=spring&logoColor=white) ![Jackson](https://img.shields.io/badge/Jackson-000000?style=flat-square&logo=json&logoColor=white) ![JWT](https://img.shields.io/badge/JWT-RS256-000000?style=flat-square&logo=json-web-tokens&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apache-kafka&logoColor=white) ![Apache Cassandra](https://img.shields.io/badge/Apache_Cassandra-1287B1?style=flat-square&logo=apache-cassandra&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-13aa52?style=flat-square&logo=mongodb&logoColor=white) ![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-425CC7?style=flat-square&logo=opentelemetry&logoColor=white) ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) ![Testcontainers](https://img.shields.io/badge/Testcontainers-2496ED?style=flat-square&logo=testcontainers&logoColor=white) ![JUnit5](https://img.shields.io/badge/JUnit_5-25A162?style=flat-square&logo=junit5&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Zero--Trust](https://img.shields.io/badge/Zero--Trust-mTLS%20%7C%20SCRAM-red?style=flat-square)
---
## 🏗️ Featured Projects

## Valoq Message Service
**Real-time messaging backend built with Netty, Cassandra & Redis Pub/Sub**
- **Custom binary TCP protocol with full lifecycle receipts** — Designed a 12-byte framed protocol (magic/version/opcode/streamId/bodyLength) over Netty with JWT-authenticated sessions, and implemented end-to-end delivery/read watermarking so senders get confirmed receipts when recipients acknowledge messages.
- **Horizontally scalable cross-node fan-out** — Built Redis Pub/Sub-based routing so any node can deliver messages to users connected elsewhere, backed by a `ConnectionTracker` registry supporting multiple concurrent channels per user.
- **Cassandra data model tuned for scale** — Partitioned events by `(conversation_id, time_bucket, hash_bucket)` to avoid hot partitions while preserving chronological ordering via time-based UUIDs, with a per-user `user_events` inbox enabling cursor-based SYNC recovery for offline clients.
- **Adversarial test suite with Testcontainers** — Wrote 80+ end-to-end tests covering protocol fuzzing (garbage bytes, unknown opcodes, truncated/oversized frames), backpressure bursts above high watermark, reconnect cycles, 1 MB payload round-trips, and multi-client concurrent pipelining — all against real Cassandra 5.0 and Redis 8.8.3 containers.
- **Graceful degradation under failure** — Server survives 50× sequential malformed connections, abrupt TCP disconnects, invalid magic/version bytes, and negative frame lengths without poisoning subsequent sessions, while malformed SEND/SYNC commands return structured `ERROR` frames without killing authenticated connections.

### 2. [E-Commerce Application](https://github.com/ashenscribe/Titan)
- **No Lost or Duplicate Orders:** Used the transactional outbox pattern with Debezium and Kafka so every accepted order is published exactly once in effect; chaos tests that killed services mid-order showed `0` lost and `0` duplicate orders across [N] runs.
- **No Lost or Duplicate Orders:** Outbox Pattern + Kafka for reliable eventual consistency across services
- **Stock That Never Oversells:** Built concurrency-safe inventory reservations with automatic expiry; in a test of `1,000` simultaneous buyers for `10` units, exactly `10` orders succeeded.
- **Order Workflow With Automatic Undo:** Designed an order saga (state machine) across `order`, `payment`, and `inventory` services; when payment fails, reserved stock is released automatically, covered by one test per failure path.
- **Stays Up When Services Fail:** Added timeouts, retries, circuit breakers, and idempotency keys on service calls, so a slow or crashed payment service degrades gracefully and a retried request never charges twice.
---
## 📚 Education
**National Institute of Technology (NIT) Srinagar**  
B.Tech in Computer Science & Engineering (August 2024 – Present)

---
## 📫 Connect with Me
- [GitHub](https://github.com/ashenscribe)
- [Email](mailto:rishabhsaraswat17@gmail.com)
- [Portfolio](https://omnicoder77.github.io/omniCoder77/)
