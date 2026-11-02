# Hi there, I'm Rishabh Saraswat 👋
## 🚀 Apache Cassandra CEP-59 Mentee (Apache Software Foundation)
---
## 🚀 Open Source Contributions
### Apache Cassandra

- **Cassandra Enhancement Proposal - 59 ([In Progress](https://github.com/apache/cassandra/pull/4953)):** Implementing in-band connection draining to enable graceful client disconnection during rolling maintenance and reduce ReadTimeouts in multi-node clusters.

- **Implemented Guardrail for Unprepared Statements:** Developed a new Guardrail configuration to detect, warn, or reject queries that bypass the prepared statement cache (cache misses).
  [Commit](https://github.com/apache/cassandra/commit/eabd2a27f5555a50cba6dc8b74d1f246a91081c0) | [PR #4596](https://github.com/apache/cassandra/pull/4596) | [CASSANDRA-21139](https://issues.apache.org/jira/browse/CASSANDRA-21139)

- **Added a new dispatching technique providing QoS (Quality of Service) to cassandra:(In review)** Developed a new configuration that allows users to choose a QoS servicing mechanism giving ~26% faster reads, +16.8% more throughput. [PR](https://github.com/apache/cassandra/pull/5195) | [Ticket](https://issues.apache.org/jira/browse/CASSANDRA-21571)

- **Driver authentication Timeout Config(In Review):** Developed a new configuration that sets a hard limit for clients to authenticate themselves, dropping connection if client doesn't authenticates itself. [PR](https://github.com/apache/cassandra/pull/5261) | [Ticket](https://issues.apache.org/jira/browse/CASSANDRA-21756)

- **Add Sanitizing of client key-value pair options in driver handshake(In Review):** Added sanitization of invalid values sent by driver in initial handshake. [PR](https://github.com/apache/cassandra/pull/5260) | [Ticket](https://issues.apache.org/jira/browse/CASSANDRA-21755)

- **Security:** Resolved TLS 1.3 connectivity issues in cassandra-stress; implemented Perfect Forward
Secrecy via updated cipher suites to meet modern encryption standards.
Addresses: [Commit](https://github.com/apache/cassandra/commit/9d89b47c68a6b476135c04b633e7d080a8ebe65f) | [PR](https://github.com/apache/cassandra/pull/4499) | [CASSANDRA-21007](https://issues.apache.org/jira/browse/CASSANDRA-21007)

- **Memory Optimization (PR Under Review):** Eliminated unnecessary String instance creation during MBean registration to reduce memory overhead.
  Pending Commit | [PR#4548](https://github.com/apache/cassandra/pull/4548) |  [CASSANDRA-20446](https://issues.apache.org/jira/browse/CASSANDRA-20446)

- **Testing Infrastructure:** Engineered a simulation script for "blocked" data scenarios; verified storage utility accuracy for file sizes and date formats, optimizing disk-space diagnostics.
  Addresses: [Commit](https://github.com/apache/cassandra/commit/6bf598dcdec8cc81a870fc5363308022bf11aead) | [PR](https://github.com/apache/cassandra/pull/3993) | [CASSANDRA-20448](https://issues.apache.org/jira/browse/CASSANDRA-20448)

---

## 🛠 Tech Stack 
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white) ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white) ![Spring WebFlux](https://img.shields.io/badge/Spring_WebFlux-6DB33F?style=flat-square&logo=spring&logoColor=white) ![Project Reactor](https://img.shields.io/badge/Project_Reactor-6DB33F?style=flat-square&logo=spring&logoColor=white) ![gRPC](https://img.shields.io/badge/gRPC-244c5a?style=flat-square&logo=grpc&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apache-kafka&logoColor=white) ![Apache Cassandra](https://img.shields.io/badge/Apache_Cassandra-1287B1?style=flat-square&logo=apache-cassandra&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-13aa52?style=flat-square&logo=mongodb&logoColor=white) ![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Zero--Trust](https://img.shields.io/badge/Zero--Trust-mTLS%20%7C%20SCRAM-red?style=flat-square)
---
## 🏗️ Featured Projects

### 1. [Communication Application](https://github.com/ashenscribe/Valoq) – Flagship Project
- **Authentication & Security:** Built a Netty-based auth service for registration, credential verification, RSA-signed JWTs, public-key distribution, and token validation.
- **Custom Binary Protocol:** Designed a binary TCP protocol supporting stream multiplexing, request correlation, and server-initiated events over persistent connections.
- **Distributed Messaging & Persistence:** Implemented asynchronous message routing, Cassandra-backed event storage, Redis connection management, acknowledgements, and cursor-based offline replay.
- **Flow Control & Reliability:** Implemented in-flight limits, high/low-watermark backpressure, delivery/read receipts, and connection lifecycle management.
- **Testing & Observability:** Built containerized tests for concurrency, protocol fuzzing, reconnection, and failures; achieved 85% coverage and integrated GitHub Actions and OpenTelemetry.

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
