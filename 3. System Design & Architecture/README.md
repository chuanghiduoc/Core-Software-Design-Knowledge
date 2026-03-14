# 3. System Design & Architecture

> Kiến thức thiết kế hệ thống ở cấp độ production — từ cách tổ chức code trong 1 service
> đến cách thiết kế hệ thống phân tán phục vụ hàng triệu users.

---

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 3.1 | [Clean Architecture & Hexagonal](./3.1-Clean-Hexagonal-Architecture.md) | Layered Architecture, Hexagonal/Ports & Adapters, Clean Architecture, Vertical Slice |
| 3.2 | [Monolith · Modular Monolith · Microservices](./3.2-Monolith-vs-Microservices.md) | Khi nào dùng gì, migration path, communication patterns |
| 3.3 | [Event-Driven Architecture](./3.3-Event-Driven-Architecture.md) | Event types, Event Bus, Message Brokers, Saga, Choreography vs Orchestration |
| 3.4 | [CQRS & Event Sourcing](./3.4-CQRS-Event-Sourcing.md) | Command/Query separation ở system level, Event Store, Projections, Snapshots |
| 3.5 | [API Design](./3.5-API-Design.md) | REST, GraphQL, tRPC, gRPC, Versioning, Pagination, Error handling |
| 3.6 | [Data Architecture](./3.6-Data-Architecture.md) | Schema design, SQL vs NoSQL, Migrations, Caching strategies, Data consistency |
| 3.7 | [Scalability & Performance](./3.7-Scalability-Performance.md) | Horizontal/Vertical scaling, Load balancing, Sharding, CDN, Connection pooling |
| 3.8 | [Resilience & Fault Tolerance](./3.8-Resilience-Fault-Tolerance.md) | Circuit Breaker, Retry, Bulkhead, Timeout, Graceful degradation, Chaos engineering |
| 3.9 | [Observability](./3.9-Observability.md) | Structured logging, Metrics, Distributed tracing, Alerting, Dashboards |
| 3.10 | [Security Architecture](./3.10-Security-Architecture.md) | Authentication, Authorization (RBAC/ABAC), Input validation, Secrets, Encryption, OWASP Top 10, Audit |
| 3.11 | [Infrastructure & Deployment](./3.11-Infrastructure-Deployment.md) | Docker, CI/CD, Infrastructure as Code, Zero-downtime deployment, Configuration management |
| 3.12 | [Integration Patterns](./3.12-Integration-Patterns.md) | Anti-Corruption Layer, API Gateway/BFF, Webhooks, Third-party best practices, CDC, ETL |
| 3.13 | [Distributed Data](./3.13-Distributed-Data.md) | CAP theorem, Consistency models, Distributed transactions, Saga, Partitioning, Conflict resolution |
| 3.14 | [Serverless & Edge](./3.14-Serverless-Edge.md) | Lambda/Functions, Edge computing, Cloudflare Workers, Edge databases, Cost comparison |
| 3.15 | [Disaster Recovery](./3.15-Disaster-Recovery.md) | RTO/RPO, Backup strategies, HA architectures, Incident response, Chaos engineering, Runbooks |
| 3.16 | [Cost Architecture & FinOps](./3.16-Cost-Architecture.md) | Cost-aware decisions, Cloud optimization, Right-sizing, Cost monitoring, Anomaly detection |
| 3.17 | [Documentation & ADR](./3.17-Documentation-ADR.md) | Architecture Decision Records, Documentation strategy, API docs, Diagrams as code |
| 3.18 | [System Evolution](./3.18-System-Evolution.md) | Technical debt management, Refactoring strategies, Migration patterns, Backward compatibility, System lifecycle |

## Triết lý

```
Architecture is about the DECISIONS that are HARD TO CHANGE later.
— Everything else is implementation detail.
```

Khi thiết kế hệ thống, ưu tiên theo thứ tự:

1. **Correctness** — Hệ thống phải đúng trước
2. **Availability** — Phải hoạt động khi cần
3. **Maintainability** — Team phải hiểu và sửa được
4. **Scalability** — Phải handle được growth
5. **Performance** — Phải đủ nhanh (nhưng đừng premature optimize)
