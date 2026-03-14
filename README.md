# Core Software Design Knowledge

> Bo kien thuc thiet ke phan mem cot loi — tu code-level den system-level den people-level.
> Viet bang tieng Viet, chuyen sau TypeScript, goc nhin cua ky su hang dau the gioi.

---

## Tong quan

**67 files | 40,574+ dong** kien thuc thiet ke phan mem, bao gom:

- Moi concept deu co **Bad vs Good** code examples
- Tat ca code examples deu **TypeScript production-grade**
- Moi topic deu co **khi nao dung / khi nao KHONG dung**
- Tu **ly thuyet** den **real-world case studies**

## Muc luc

### Foundation (Nen tang)

| # | Section | Mo ta | Files |
|---|---------|-------|-------|
| 1 | [Design Principles](./1.%20Design%20Principles/) | SOLID, DRY/KISS/YAGNI, Composition over Inheritance, SoC, Law of Demeter, Fail Fast, Immutability | 7 |
| 2 | [Design Patterns](./2.%20Design%20Patterns/) | 23 GoF Patterns voi TypeScript hien dai — Creational, Structural, Behavioral | 6 |

### Architecture (Kien truc)

| # | Section | Mo ta | Files |
|---|---------|-------|-------|
| 3 | [System Design & Architecture](./3.%20System%20Design%20%26%20Architecture/) | Clean/Hexagonal Architecture, Microservices, EDA, CQRS, API Design, Security, Infra, DR, Cost | 19 |
| 4 | [Domain-Driven Design](./4.%20Domain-Driven%20Design%20(DDD)/) | Strategic DDD (Bounded Contexts, Context Mapping), Tactical DDD (Entities, Value Objects, Aggregates) | 4 |

### Data & Distribution (Du lieu & Phan tan)

| # | Section | Mo ta | Files |
|---|---------|-------|-------|
| 5 | [Data Modeling & Database Design](./5.%20Data%20Modeling%20%26%20Database%20Design/) | Relational modeling, Indexing, NoSQL, Data lifecycle, GDPR | 5 |
| 6 | [Distributed Systems](./6.%20Distributed%20Systems%20fundamentals/) | CAP/PACELC, Consensus (Raft), Vector Clocks, Consistent Hashing, Distributed Locking | 6 |

### Operations (Van hanh)

| # | Section | Mo ta | Files |
|---|---------|-------|-------|
| 7 | [Observability & Operational Thinking](./7.%20Observability%20%26%20Operational%20thinking/) | SRE (SLI/SLO/SLA), Advanced Observability, Alerting, Production Readiness | 5 |
| 8 | [Security by Design](./8.%20Security%20by%20Design/) | Threat Modeling (STRIDE), OAuth2/OIDC, Authorization (RBAC/ABAC/ReBAC), OWASP Top 10 | 5 |

### Quality & Decisions (Chat luong & Quyet dinh)

| # | Section | Mo ta | Files |
|---|---------|-------|-------|
| 9 | [Testing Strategy](./9.%20Testing%20Strategy%20(kh%C3%B4ng%20ph%E1%BA%A3i%20vi%E1%BA%BFt%20test)/) | Testing philosophy, Unit/Integration/E2E strategy, Contract testing, Testing architecture | 5 |
| 10 | [Technical Decision Making](./10.%20Technical%20Decision%20Making/) | Decision frameworks, RFC process, Build vs Buy, Communication & Leadership | 5 |

## Danh cho ai?

- **Junior Engineers**: Doc tu Section 1 → 2 → 9 de xay nen tang
- **Mid-level Engineers**: Focus Section 3 → 4 → 5 de len level
- **Senior Engineers**: Deep dive Section 6 → 7 → 8 → 10 de master production systems
- **Tech Leads / CTOs**: Section 10 + 3 (architecture decisions) + 7 (operational excellence)

## Lo trinh hoc de xuat

```
Phase 1: Foundations (2-4 tuan)
  1. Design Principles → hieu "tai sao" truoc khi hieu "the nao"
  2. Design Patterns → cong cu tu duy, khong phai recipe

Phase 2: Architecture (4-6 tuan)
  3. System Design → buc tranh toan canh
  4. DDD → khi domain phuc tap
  5. Data Modeling → nen tang cua moi he thong

Phase 3: Production (4-6 tuan)
  6. Distributed Systems → hieu he thong phan tan
  7. Observability → van hanh production
  8. Security → bao ve he thong

Phase 4: Mastery (ongoing)
  9. Testing Strategy → dam bao chat luong
  10. Technical Decision Making → ky nang cua senior/lead
```

## Nguyen tac thiet ke tai lieu nay

1. **Thuc te truoc ly thuyet** — Moi concept bat dau tu van de thuc te
2. **TypeScript-first** — Code chay duoc, khong phai pseudocode
3. **Trade-offs** — Khong co giai phap hoan hao, chi co trade-offs
4. **Khi nao KHONG dung** — Biet khi nao KHONG ap dung quan trong hon biet ap dung
5. **Production-grade** — Viet cho he thong thuc, khong phai bai tap

## License

[MIT](./LICENSE)
