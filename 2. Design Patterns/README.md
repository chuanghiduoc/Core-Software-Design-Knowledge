# 2. Design Patterns

> 23 Design Patterns của Gang of Four (GoF), viết lại hoàn toàn cho TypeScript hiện đại.
> Mỗi pattern đi kèm: Vấn đề thực tế → Giải pháp → Code production-ready → Khi nào dùng/không dùng.

---

## Design Patterns là gì?

Design Patterns là **giải pháp đã được chứng minh** cho các vấn đề thiết kế phần mềm lặp đi lặp lại. Chúng KHÔNG phải là:
- ❌ Code sẵn để copy-paste
- ❌ Luật bắt buộc phải tuân theo
- ❌ Thước đo "trình độ" (dùng nhiều pattern ≠ giỏi)

Chúng LÀ:
- ✅ **Ngôn ngữ chung** để team giao tiếp ("dùng Strategy ở đây" → ai cũng hiểu)
- ✅ **Công cụ tư duy** — biết nhiều pattern = nhiều lựa chọn thiết kế hơn
- ✅ **Kinh nghiệm đúc kết** từ hàng triệu dự án thực tế

## Lộ trình học

### Tier 1 — Dùng hàng ngày (học trước)
| Pattern | Nhóm | Tần suất sử dụng |
|---------|-------|-------------------|
| **Strategy** | Behavioral | ★★★★★ |
| **Observer** | Behavioral | ★★★★★ |
| **Factory Method** | Creational | ★★★★★ |
| **Builder** | Creational | ★★★★☆ |
| **Decorator** | Structural | ★★★★☆ |
| **Adapter** | Structural | ★★★★☆ |
| **Facade** | Structural | ★★★★☆ |
| **Command** | Behavioral | ★★★★☆ |

### Tier 2 — Dùng thường xuyên
| Pattern | Nhóm | Tần suất sử dụng |
|---------|-------|-------------------|
| **Singleton** | Creational | ★★★☆☆ |
| **Proxy** | Structural | ★★★☆☆ |
| **State** | Behavioral | ★★★☆☆ |
| **Template Method** | Behavioral | ★★★☆☆ |
| **Chain of Responsibility** | Behavioral | ★★★☆☆ |
| **Composite** | Structural | ★★★☆☆ |
| **Iterator** | Behavioral | ★★★☆☆ |

### Tier 3 — Dùng khi cần
| Pattern | Nhóm | Tần suất sử dụng |
|---------|-------|-------------------|
| **Abstract Factory** | Creational | ★★☆☆☆ |
| **Prototype** | Creational | ★★☆☆☆ |
| **Bridge** | Structural | ★★☆☆☆ |
| **Flyweight** | Structural | ★★☆☆☆ |
| **Mediator** | Behavioral | ★★☆☆☆ |
| **Memento** | Behavioral | ★★☆☆☆ |
| **Visitor** | Behavioral | ★★☆☆☆ |
| **Interpreter** | Behavioral | ★☆☆☆☆ |

## Mục lục tài liệu

| # | Tài liệu | Patterns |
|---|----------|----------|
| 2.1 | [Creational Patterns](./2.1-Creational-Patterns.md) | Singleton, Factory Method, Abstract Factory, Builder, Prototype |
| 2.2 | [Structural Patterns](./2.2-Structural-Patterns.md) | Adapter, Bridge, Composite, Decorator, Facade, Flyweight, Proxy |
| 2.3 | [Behavioral Patterns — Phần 1](./2.3-Behavioral-Patterns-Part1.md) | Strategy, Observer, Command, Chain of Responsibility, Iterator, Mediator |
| 2.4 | [Behavioral Patterns — Phần 2](./2.4-Behavioral-Patterns-Part2.md) | State, Template Method, Memento, Visitor, Interpreter |
| 2.5 | [Patterns trong thực tế](./2.5-Patterns-In-Practice.md) | So sánh, kết hợp patterns, case studies production, anti-patterns |

## Nguyên tắc khi dùng patterns

```
1. Đừng tìm pattern rồi áp vào bài toán.
   Hãy hiểu bài toán rồi nhận ra pattern phù hợp.

2. Pattern đơn giản nhất giải quyết được vấn đề = pattern tốt nhất.

3. Nếu code không có pattern nào mà vẫn sạch, rõ ràng → hoàn hảo.
   Pattern là công cụ, không phải mục tiêu.

4. Trong TypeScript hiện đại, nhiều pattern đã được ngôn ngữ/framework
   hỗ trợ sẵn. Đừng re-implement từ đầu khi không cần.
```
