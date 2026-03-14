# 9. Testing Strategy

> Chiến lược testing không phải là "viết thêm test" — mà là **biết test CÁI GÌ, Ở ĐÂU, BAO NHIÊU, và TẠI SAO**.
> Một kỹ sư hàng đầu không đo lường bằng test coverage — mà đo bằng **confidence mỗi lần deploy**.

---

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 9.1 | [Testing Philosophy](./9.1-Testing-Philosophy.md) | Test Pyramid vs Trophy vs Diamond, ROI analysis, TDD, flaky tests, testing quadrant |
| 9.2 | [Unit Testing Strategy](./9.2-Unit-Testing-Strategy.md) | Sociable vs Solitary, mock guidelines, domain testing, property-based & mutation testing |
| 9.3 | [Integration & E2E Testing](./9.3-Integration-E2E-Testing.md) | Database tests, API tests, contract testing (Pact), E2E architecture, performance & chaos testing |
| 9.4 | [Testing Architecture](./9.4-Testing-Architecture.md) | Design for testability, CI/CD pipeline, coverage metrics, microservices & event-driven testing |

## Triết lý tổng quan

Testing là một **investment**, không phải tax. Mỗi test bạn viết phải trả lời được câu hỏi: **"Test này bảo vệ team khỏi bug gì?"** Nếu không trả lời được — đó là test thừa.

### Công thức của testing strategy đúng

```
Confidence = f(test quality, test coverage, test speed)
ROI = Bugs_caught / (Time_to_write + Time_to_maintain)
```

- **Test nhiều** không có nghĩa **test tốt**
- **100% coverage** không có nghĩa **0 bugs**
- **Test chậm** nghĩa là **developer không chạy test**
- **Flaky tests** phá hủy trust nhanh hơn không có test

### Kim chỉ nam

1. **Test behaviors, not implementations** — Test cái hệ thống LÀM, không phải cách nó LÀM
2. **Fast feedback loop** — Test phải chạy trong giây, không phải phút
3. **Deterministic** — Cùng input, cùng kết quả, mọi lúc, mọi nơi
4. **Independent** — Mỗi test đứng một mình, không phụ thuộc thứ tự chạy
5. **Meaningful** — Mỗi test thất bại phải cho bạn biết CHÍNH XÁC cái gì sai

### Anti-patterns phổ biến

```
❌ "Viết test cho mọi function" → Overtesting, test bị gắn chặt vào implementation
❌ "Coverage phải 90%+"       → Vanity metric, test getter/setter vô nghĩa
❌ "Mock hết dependencies"    → Test không còn phản ánh reality
❌ "E2E test hết mọi flow"    → Slow, flaky, expensive
❌ "Test sau khi code xong"   → Test trở thành afterthought, bỏ qua edge cases
```

### Mindset của kỹ sư hàng đầu về testing

```
"Tôi không viết test vì sếp bắt. Tôi viết test vì tôi muốn NGỦ NGON
 mỗi tối sau khi deploy production."

"Test tốt nhất là test mà khi nó fail, tôi biết CHÍNH XÁC phải fix ở đâu
 trong vòng 30 giây."

"Nếu phải chọn giữa 100 unit tests và 5 integration tests cover đúng
 critical paths — tôi chọn 5 integration tests."
```
