# 5. Data Modeling & Database Design

> Thiết kế dữ liệu là nền tảng quyết định sự sống còn của hệ thống. Schema sai thì code hay đến mấy
> cũng không cứu được. Một senior engineer giỏi nhìn vào schema là biết hệ thống hoạt động thế nào.

---

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 5.1 | [Relational Modeling](./5.1-Relational-Modeling.md) | Normalization (1NF → BCNF), Denormalization, ER Modeling, Schema patterns (polymorphic, EAV, temporal, soft delete, audit trail), Constraints, Multi-tenant SaaS design |
| 5.2 | [Indexing & Query Optimization](./5.2-Indexing-Query-Optimization.md) | B-tree/Hash/GIN/GiST/BRIN, Index strategy, EXPLAIN ANALYZE, Query anti-patterns (N+1, SELECT *), Optimization techniques, Connection pooling |
| 5.3 | [NoSQL Data Modeling](./5.3-NoSQL-Data-Modeling.md) | Document DB (MongoDB), Key-Value (Redis), Wide-column (Cassandra), Graph (Neo4j), Search (Elasticsearch), Time-series, Polyglot persistence |
| 5.4 | [Data Lifecycle](./5.4-Data-Lifecycle.md) | Zero-downtime migrations, Schema evolution, Backup/Recovery, Archival, GDPR compliance, Data seeding, Database branching |

## Triết lý

```
Data outlives code. Applications are rewritten; data schemas echo forever.
— Bất kỳ senior engineer nào đã từng maintain hệ thống 5+ năm
```

Khi thiết kế data model, ưu tiên theo thứ tự:

1. **Correctness** — Data phải đúng, constraint phải chặt. Sai data = sai business
2. **Integrity** — Không bao giờ để hệ thống ở trạng thái inconsistent
3. **Evolvability** — Schema phải thay đổi được mà không downtime
4. **Performance** — Query phải đủ nhanh, nhưng đừng sacrifice correctness cho speed
5. **Simplicity** — Schema đơn giản nhất có thể, nhưng không đơn giản hơn

## Nguyên tắc vàng

### 1. Schema là API contract lâu dài nhất

Code có thể refactor trong 1 sprint. Schema migration trên 100M rows mất hàng tuần và có thể lock production.

### 2. Normalize trước, denormalize khi có evidence

Đừng denormalize vì "chắc sẽ cần tối ưu". Normalize trước, đo performance, rồi mới denormalize có chọn lọc.

### 3. Constraints ở database, KHÔNG chỉ ở application

Application code có bugs. Developers quên validate. Nhưng database constraints LUÔN enforce — đó là safety net cuối cùng.

### 4. Chọn database phù hợp với access pattern

Không phải mọi thứ đều là PostgreSQL. Không phải mọi thứ đều cần MongoDB. Hiểu access pattern rồi mới chọn DB.

### 5. Plan for data growth từ ngày đầu

Table 1000 rows và 100M rows hoạt động hoàn toàn khác. Schema design phải nghĩ đến scale từ đầu — nhưng implement đơn giản trước.
