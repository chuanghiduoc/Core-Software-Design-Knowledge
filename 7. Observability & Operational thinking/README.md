# 7. Observability & Operational Thinking

> "Hope is not a strategy." — Google SRE Book
>
> Production không phải là nơi bạn "deploy xong rồi quên". Production là nơi bạn phải
> **nhìn thấy**, **hiểu được**, và **phản ứng kịp** với mọi thứ đang xảy ra.

---

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 7.1 | [SRE Principles](./7.1-SRE-Principles.md) | SRE philosophy, SLI/SLO/SLA, Error Budgets, Toil, Risk Analysis |
| 7.2 | [Advanced Observability](./7.2-Advanced-Observability.md) | Structured logging nâng cao, RED/USE methods, OpenTelemetry deep dive, Correlation across pillars |
| 7.3 | [Alerting & On-Call](./7.3-Alerting-Oncall.md) | Alert design, On-call rotation, Incident management, Postmortem, Runbooks |
| 7.4 | [Production Readiness](./7.4-Production-Readiness.md) | Readiness checklist, Capacity planning, Graceful shutdown, Feature flags, Node.js profiling |

## Mối quan hệ với Section 3.9

Section 3.9 đã giới thiệu **nền tảng observability**: three pillars (logs, metrics, traces), structured logging cơ bản, metrics collector đơn giản, distributed tracing concept, và alerting rules.

Section 7 đi **sâu hơn rất nhiều** vào khía cạnh **vận hành thực tế**:

```
Section 3.9 (Foundation)          Section 7 (Operational Depth)
─────────────────────────         ─────────────────────────────
What are logs/metrics/traces?  →  How to design a complete observability platform?
Basic structured logging       →  Correlation IDs, context propagation, log aggregation pipelines
Simple metrics collector       →  RED/USE methods, custom business metrics with Prometheus
Trace context propagation      →  Full OpenTelemetry setup, sampling strategies, trace analysis
Alert rules examples           →  Alert design philosophy, on-call, incident management, postmortems
(not covered)                  →  SRE principles, SLI/SLO/SLA, Error Budgets
(not covered)                  →  Production readiness, graceful shutdown, feature flags
(not covered)                  →  Node.js profiling, memory leak detection, capacity planning
```

## Triết lý

```
"You build it, you run it." — Werner Vogels, CTO Amazon

Operational excellence không phải trách nhiệm của ops team.
Nó là trách nhiệm của MỌI engineer.
```

### 5 Trụ cột của Operational Thinking

```
1. VISIBILITY    — Bạn có nhìn thấy hệ thống đang làm gì không?
2. RELIABILITY   — Hệ thống có đáng tin cậy ở mức users cần không?
3. PREPAREDNESS  — Bạn có sẵn sàng khi sự cố xảy ra không?
4. RESILIENCE    — Hệ thống có tự phục hồi được không?
5. EVOLUTION     — Bạn có liên tục cải thiện operations không?
```

### Mindset của một SRE / Production Engineer

1. **Measure everything** — Không đo lường được thì không cải thiện được
2. **Automate toil** — Việc gì lặp lại, hãy tự động hóa
3. **Plan for failure** — Hệ thống SẼ hỏng, câu hỏi là KHI NÀO và bạn PHẢN ỨNG thế nào
4. **Blameless culture** — Đổ lỗi cho người không giúp hệ thống tốt hơn
5. **Balance velocity and reliability** — Ship nhanh nhưng không phá production
