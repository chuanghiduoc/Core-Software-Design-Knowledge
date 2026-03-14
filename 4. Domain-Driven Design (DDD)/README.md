# 4. Domain-Driven Design (DDD)

> Phương pháp thiết kế phần mềm đặt **domain logic** — bài toán kinh doanh thực sự —
> vào trung tâm mọi quyết định kỹ thuật.
> DDD không phải framework, không phải thư viện. Nó là **tư duy** để giải quyết complexity.

---

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 4.1 | [Strategic DDD](./4.1-Strategic-DDD.md) | Ubiquitous Language, Bounded Contexts, Context Mapping (8 patterns), Subdomains, Event Storming |
| 4.2 | [Tactical DDD](./4.2-Tactical-DDD.md) | Entity, Value Object, Aggregate, Domain Event, Domain Service, Repository, Factory, Specification — full TypeScript |
| 4.3 | [DDD In Practice](./4.3-DDD-In-Practice.md) | Project structure, DDD + Hexagonal, Aggregate design rules, Anti-patterns, CQRS, Testing, Case study |

## Triết lý

```
The goal of DDD is to create a shared understanding of the domain
between developers and domain experts — and to embed that understanding
directly into the code.
— Eric Evans, "Domain-Driven Design" (2003)
```

### Khi nào NÊN dùng DDD?

- Domain phức tạp, nhiều business rules thay đổi liên tục
- Team cần giao tiếp thường xuyên với domain experts
- Hệ thống sống lâu (5+ năm), cần maintainability cao
- Nhiều team cùng làm việc trên 1 product lớn (cần bounded contexts rõ ràng)

### Khi nào KHÔNG nên dùng DDD?

- CRUD đơn giản (admin panel, landing page, internal tool nhỏ)
- Prototype / MVP cần ship nhanh trong 2 tuần
- Team chỉ có 1-2 developers, domain đơn giản
- Không có access tới domain experts

### DDD Pyramid — Thứ tự học

```
          ┌───────────┐
          │ Strategic  │  ← Học trước: hiểu bài toán, chia boundaries
          │    DDD     │
          ├───────────┤
          │ Tactical   │  ← Học sau: patterns cho implementation
          │    DDD     │
          ├───────────┤
          │ Practice   │  ← Áp dụng: project structure, testing, anti-patterns
          │ & Patterns │
          └───────────┘
```

> **Sai lầm phổ biến nhất**: Nhảy thẳng vào Tactical DDD (Entity, Value Object, Repository)
> mà bỏ qua Strategic DDD. Kết quả là code "DDD" nhưng không giải quyết đúng bài toán.
