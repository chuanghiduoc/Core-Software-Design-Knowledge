# 10. Technical Decision Making

> Phần "trí tuệ" của software engineering — nơi tất cả kiến thức kỹ thuật từ các chương trước
> được kết nối thành **khả năng ra quyết định**. Đây là thứ phân biệt một senior engineer
> với một junior, một tech lead với một IC, một CTO với một developer giỏi.

---

## Tại sao chương này quan trọng nhất

Bạn có thể biết tất cả Design Patterns, nắm vững SOLID, hiểu rõ Distributed Systems —
nhưng nếu không biết **khi nào dùng cái gì**, **tại sao chọn A thay vì B**, và **làm sao
truyền đạt quyết định đó** cho team và stakeholders, thì kiến thức đó chỉ là lý thuyết suông.

```
Knowledge × Decision-Making = Engineering Impact
```

Một engineer giỏi không phải người biết nhiều nhất, mà là người **ra quyết định đúng nhất
trong điều kiện thiếu thông tin và áp lực thời gian**.

---

## Mục lục

| # | Tài liệu | Nội dung |
|---|----------|----------|
| 10.1 | [Decision Frameworks](./10.1-Decision-Frameworks.md) | Framework tư duy ra quyết định: trade-off analysis, reversibility, DACI, decision matrix, second-order thinking |
| 10.2 | [Technical RFC Process](./10.2-Technical-RFC-Process.md) | Quy trình RFC/ADR/Design Doc, template, review process, ví dụ thực tế |
| 10.3 | [Build vs Buy](./10.3-Build-vs-Buy.md) | Framework đánh giá Build vs Buy, TCO, open source evaluation, vendor lock-in |
| 10.4 | [Communication & Leadership](./10.4-Communication-Leadership.md) | Truyền đạt quyết định, quản lý risk, estimation, mentoring, technical culture |

---

## Triết lý tổng quan

### Điều mà trường học không dạy

Trong trường, mọi bài tập đều có **đáp án đúng duy nhất**. Trong thực tế:

- Mọi quyết định đều là **trade-off** — không có giải pháp hoàn hảo
- Bạn luôn quyết định với **thông tin không đầy đủ** — chờ đủ thông tin = quá muộn
- **Context quyết định tất cả** — giải pháp đúng cho company A có thể là thảm họa cho company B
- **Timing quan trọng ngang chất lượng** — quyết định đúng nhưng muộn 6 tháng = quyết định sai
- **Quyết định tốt nhất có thể vẫn cho kết quả xấu** — và ngược lại

### Cách đọc chương này

```
10.1 Decision Frameworks    → HỌC CÁCH SUY NGHĨ
10.2 Technical RFC Process  → HỌC CÁCH GHI CHÉP & REVIEW
10.3 Build vs Buy           → HỌC CÁCH ĐÁNH GIÁ LỰA CHỌN
10.4 Communication          → HỌC CÁCH TRUYỀN ĐẠT & DẪN DẮT
```

Mỗi phần xây dựng trên phần trước. Decision Frameworks cho bạn công cụ tư duy,
RFC Process cho bạn quy trình ghi lại quyết định, Build vs Buy áp dụng framework
vào một loại quyết định cực kỳ phổ biến, và Communication giúp bạn biến quyết định
thành hành động thực tế trong tổ chức.

### Kết nối với các chương trước

| Chương | Kết nối với Decision Making |
|--------|-----------------------------|
| 1. Design Principles | Principles giúp bạn biết hướng đi, Decision Making giúp bạn chọn con đường |
| 2. Design Patterns | Patterns là công cụ, Decision Making giúp bạn chọn đúng công cụ |
| 3. System Architecture | Architecture là bản vẽ, Decision Making là quá trình vẽ |
| 4. DDD | DDD cho bạn ngôn ngữ chung, Decision Making cho bạn quy trình chung |
| 5. Data Modeling | Data model là nền tảng, quyết định sai ở đây = pain lâu dài |
| 6. Distributed Systems | Hệ thống phân tán = nhiều trade-off hơn = cần framework tốt hơn |
| 7. Observability | Dữ liệu quan sát giúp validate quyết định |
| 8. Security | Security trade-offs luôn cần cân nhắc |
| 9. Testing | Testing strategy phản ánh chất lượng quyết định kỹ thuật |

---

## Dấu hiệu của một người ra quyết định giỏi

```
Junior:   "Chúng ta nên dùng microservices vì Netflix dùng"
Mid:      "Chúng ta nên dùng microservices vì X, Y, Z"
Senior:   "Dựa vào context của chúng ta, monolith phù hợp hơn vì A, B, C.
           Microservices sẽ là bước tiếp theo khi chúng ta đạt threshold D."
Staff+:   "Đây là decision framework cho team. Mỗi team có thể tự đánh giá
           dựa trên criteria này, và escalate khi cần."
```

> **"The mark of a great engineer is not the decisions they make,
> but the framework they use to make decisions."**
