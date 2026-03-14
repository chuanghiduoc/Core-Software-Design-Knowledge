# 6. Distributed Systems Fundamentals

> Nền tảng hệ thống phân tán dành cho kỹ sư phần mềm — từ lý thuyết đến thực chiến, tất cả ví dụ bằng TypeScript.

## Tại sao kỹ sư phần mềm cần hiểu Distributed Systems?

Trong thời đại cloud-native, **mọi hệ thống production đều là hệ thống phân tán** — dù bạn có nhận ra hay không. Khi bạn deploy một ứng dụng lên Kubernetes, gọi API sang service khác, dùng Redis cache, hay đọc từ PostgreSQL replica — bạn đang sống trong thế giới distributed systems.

Sự khác biệt giữa senior engineer và junior không chỉ ở code — mà ở khả năng **reasoning về failure modes**, hiểu **trade-offs giữa consistency và availability**, và thiết kế hệ thống **resilient by design**.

```
Monolith trên 1 server → Không có network partition, không có clock skew
Microservices trên cloud  → Mọi thứ đều có thể fail, và SẼ fail
```

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 6.1 | [Fundamental Theorems](./6.1-Fundamental-Theorems.md) | CAP, PACELC, FLP Impossibility, Two Generals, Byzantine Generals, Consistency Models |
| 6.2 | [Distributed Clocks & Ordering](./6.2-Distributed-Clocks-Ordering.md) | Wall clocks, Lamport timestamps, Vector clocks, HLC, Event ordering |
| 6.3 | [Consensus & Leader Election](./6.3-Consensus-Leader-Election.md) | Raft, Paxos, Leader election, Split-brain, Fencing tokens |
| 6.4 | [Distributed Patterns](./6.4-Distributed-Patterns.md) | Consistent Hashing, Gossip Protocol, Distributed Locking, Bloom Filters, Service Mesh |
| 6.5 | [Real-World Distributed Systems](./6.5-Real-World-Distributed.md) | DNS, Kafka, Redis Cluster, PostgreSQL Replication, Rate Limiter |

## 8 Fallacies of Distributed Computing

Peter Deutsch (Sun Microsystems) liệt kê 8 giả định sai lầm mà mọi kỹ sư mới bước vào distributed systems đều mắc phải:

| # | Fallacy | Thực tế |
|---|---------|---------|
| 1 | The network is reliable | Packet loss, network partition xảy ra hàng ngày |
| 2 | Latency is zero | Cross-region call có thể 100-300ms |
| 3 | Bandwidth is infinite | Serialization overhead, payload size matters |
| 4 | The network is secure | Zero-trust, mTLS là bắt buộc |
| 5 | Topology doesn't change | Nodes join/leave cluster liên tục |
| 6 | There is one administrator | Multi-team, multi-cloud, multi-region |
| 7 | Transport cost is zero | Serialization/deserialization, DNS lookup, TLS handshake |
| 8 | The network is homogeneous | Khác hardware, OS, network stack |

## Triết lý thiết kế Distributed Systems

### 1. Design for Failure

```
Trong distributed systems, câu hỏi không phải "liệu có fail không?"
mà là "KHI NÀO fail và fail NHƯ THẾ NÀO?"
```

### 2. Trade-offs Everywhere

Không có giải pháp hoàn hảo. Mọi quyết định đều là trade-off:
- **Consistency vs Availability** — CAP theorem
- **Consistency vs Latency** — PACELC theorem
- **Simplicity vs Resilience** — Complexity budget
- **Throughput vs Latency** — Batching trade-off

### 3. Idempotency is King

Trong môi trường network unreliable, mọi operation phải được thiết kế idempotent. Retry phải an toàn. Duplicate phải được handle.

### 4. Observe Everything

Không thể debug distributed system bằng cách đọc log trên 1 server. Cần:
- **Distributed tracing** (Jaeger, Zipkin)
- **Centralized logging** (ELK, Loki)
- **Metrics aggregation** (Prometheus, Datadog)
- **Correlation IDs** xuyên suốt mọi service

## Prerequisite Knowledge

Trước khi đọc section này, bạn nên nắm vững:
- Networking basics (TCP/IP, HTTP, DNS)
- Concurrency & parallelism
- Database fundamentals (Section 5)
- System Design basics (Section 3)
