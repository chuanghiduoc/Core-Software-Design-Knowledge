# Core Software Design Knowledge

> Bộ kiến thức thiết kế phần mềm cốt lõi — từ code-level đến system-level đến people-level.
> Viết bằng tiếng Việt, chuyên sâu TypeScript, góc nhìn của kỹ sư hàng đầu thế giới.

---

## Tổng quan

**70 files | 40,700+ dòng** kiến thức thiết kế phần mềm, bao gồm:

- Mọi concept đều có **❌ Bad vs ✅ Good** code examples
- Tất cả code examples đều **TypeScript production-grade**
- Mọi topic đều có **khi nào dùng / khi nào KHÔNG dùng**
- Từ **lý thuyết** đến **real-world case studies**

## Mục lục

### Nền tảng

| # | Section | Mô tả | Files |
|---|---------|-------|-------|
| 1 | [Design Principles](./1.%20Design%20Principles/) | SOLID, DRY/KISS/YAGNI, Composition over Inheritance, SoC, Law of Demeter, Fail Fast, Immutability | 7 |
| 2 | [Design Patterns](./2.%20Design%20Patterns/) | 23 GoF Patterns với TypeScript hiện đại — Creational, Structural, Behavioral | 6 |

### Kiến trúc

| # | Section | Mô tả | Files |
|---|---------|-------|-------|
| 3 | [System Design & Architecture](./3.%20System%20Design%20%26%20Architecture/) | Clean/Hexagonal Architecture, Microservices, EDA, CQRS, API Design, Security, Infra, DR, Cost | 19 |
| 4 | [Domain-Driven Design](./4.%20Domain-Driven%20Design%20(DDD)/) | Strategic DDD (Bounded Contexts, Context Mapping), Tactical DDD (Entities, Value Objects, Aggregates) | 4 |

### Dữ liệu & Phân tán

| # | Section | Mô tả | Files |
|---|---------|-------|-------|
| 5 | [Data Modeling & Database Design](./5.%20Data%20Modeling%20%26%20Database%20Design/) | Relational modeling, Indexing, NoSQL, Data lifecycle, GDPR | 5 |
| 6 | [Distributed Systems](./6.%20Distributed%20Systems%20fundamentals/) | CAP/PACELC, Consensus (Raft), Vector Clocks, Consistent Hashing, Distributed Locking | 6 |

### Vận hành

| # | Section | Mô tả | Files |
|---|---------|-------|-------|
| 7 | [Observability & Operational Thinking](./7.%20Observability%20%26%20Operational%20thinking/) | SRE (SLI/SLO/SLA), Advanced Observability, Alerting, Production Readiness | 5 |
| 8 | [Security by Design](./8.%20Security%20by%20Design/) | Threat Modeling (STRIDE), OAuth2/OIDC, Authorization (RBAC/ABAC/ReBAC), OWASP Top 10 | 5 |

### Chất lượng & Quyết định

| # | Section | Mô tả | Files |
|---|---------|-------|-------|
| 9 | [Testing Strategy](./9.%20Testing%20Strategy%20(kh%C3%B4ng%20ph%E1%BA%A3i%20vi%E1%BA%BFt%20test)/) | Testing philosophy, Unit/Integration/E2E strategy, Contract testing, Testing architecture | 5 |
| 10 | [Technical Decision Making](./10.%20Technical%20Decision%20Making/) | Decision frameworks, RFC process, Build vs Buy, Communication & Leadership | 5 |

## Dành cho ai?

- **Junior Engineers**: Đọc từ Section 1 → 2 → 9 để xây nền tảng
- **Mid-level Engineers**: Focus Section 3 → 4 → 5 để lên level
- **Senior Engineers**: Deep dive Section 6 → 7 → 8 → 10 để master production systems
- **Tech Leads / CTOs**: Section 10 + 3 (architecture decisions) + 7 (operational excellence)

## Lộ trình học đề xuất

```
Phase 1: Nền tảng (2-4 tuần)
  1. Design Principles → hiểu "tại sao" trước khi hiểu "thế nào"
  2. Design Patterns → công cụ tư duy, không phải recipe

Phase 2: Kiến trúc (4-6 tuần)
  3. System Design → bức tranh toàn cảnh
  4. DDD → khi domain phức tạp
  5. Data Modeling → nền tảng của mọi hệ thống

Phase 3: Production (4-6 tuần)
  6. Distributed Systems → hiểu hệ thống phân tán
  7. Observability → vận hành production
  8. Security → bảo vệ hệ thống

Phase 4: Mastery (ongoing)
  9. Testing Strategy → đảm bảo chất lượng
  10. Technical Decision Making → kỹ năng của senior/lead
```

## Nguyên tắc thiết kế tài liệu này

1. **Thực tế trước lý thuyết** — Mọi concept bắt đầu từ vấn đề thực tế
2. **TypeScript-first** — Code chạy được, không phải pseudocode
3. **Trade-offs** — Không có giải pháp hoàn hảo, chỉ có trade-offs
4. **Khi nào KHÔNG dùng** — Biết khi nào KHÔNG áp dụng quan trọng hơn biết áp dụng
5. **Production-grade** — Viết cho hệ thống thực, không phải bài tập

## License

[MIT](./LICENSE)
