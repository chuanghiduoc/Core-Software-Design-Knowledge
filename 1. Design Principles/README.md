# 1. Design Principles

> Tài liệu kiến thức thiết kế phần mềm cốt lõi — góc nhìn của kỹ sư hàng đầu, chuyên sâu TypeScript.

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 1.1 | [SOLID](./1.1-SOLID.md) | 5 nguyên lý nền tảng OOP: SRP, OCP, LSP, ISP, DIP |
| 1.2 | [DRY · KISS · YAGNI](./1.2-DRY-KISS-YAGNI.md) | 3 nguyên lý cơ bản nhất mọi kỹ sư phải nắm |
| 1.3 | [Composition over Inheritance](./1.3-Composition-over-Inheritance.md) | Tại sao composition gần như luôn thắng inheritance |
| 1.4 | [Separation of Concerns](./1.4-Separation-of-Concerns.md) | Tách biệt trách nhiệm ở mọi cấp độ |
| 1.5 | [Other Core Principles](./1.5-Other-Core-Principles.md) | Law of Demeter, Tell Don't Ask, Fail Fast, POLA, Hollywood Principle, Encapsulation, CQS |
| 1.6 | [Real-World Case Studies](./1.6-Real-World-Case-Studies.md) | Case studies thực tế, anti-patterns, và bài học từ production |

## Triết lý tổng quan

Design Principles không phải là luật bất di bất dịch — chúng là **heuristics** (quy tắc kinh nghiệm) giúp bạn đưa ra quyết định thiết kế tốt hơn. Một kỹ sư giỏi biết **khi nào áp dụng** và quan trọng hơn, biết **khi nào bẻ cong** chúng.

### Thứ tự ưu tiên khi có xung đột

```
Correctness > Clarity > Simplicity > Performance > DRY > Elegance
```

- Code đúng trước, đẹp sau
- Code dễ đọc quan trọng hơn code ngắn
- Đừng tối ưu sớm, nhưng cũng đừng thiết kế ngớ ngẩn
- Duplicate tốt hơn abstraction sai

### Mindset của một kỹ sư hàng đầu

1. **Viết code cho người đọc, không phải compiler** — Code được đọc nhiều hơn viết 10 lần
2. **Optimize for change** — Requirements luôn thay đổi, thiết kế để dễ thay đổi
3. **Make the right thing easy, the wrong thing hard** — API/interface tốt khiến người dùng khó mắc lỗi
4. **Boring is good** — Code "nhàm chán", dễ đoán là code tốt nhất
5. **Every decision is a trade-off** — Không có giải pháp hoàn hảo, chỉ có trade-offs phù hợp
