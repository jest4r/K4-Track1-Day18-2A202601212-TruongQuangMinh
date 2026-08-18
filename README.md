# Track1_Day18_MHV_NguyenThiThuong

## 1. Thông tin cá nhân và nhóm

| Thông tin                | Nội dung                                                              |
| ------------------------- | ---------------------------------------------------------------------- |
| **MHV**             | 2A202601212                                                            |
| **Họ và tên**    | Trương                                                               |
| **Tên nhóm**      | MT                                                                     |
| **Thành viên**    | Trương Quang Minh - 2A202601212; Nguyễn Thị Thương - 2A202601226 |
| **Case đã chọn** | Case A — AI Tutor: Diagnostic Refresher                               |

---

## 2. Hypothesis Problem (Day 18)

> Khi đang học một bài online và gặp một khái niệm/định nghĩa mà mình không nhớ hoặc không hiểu, học viên gặp khó khăn trong việc xác định nên ôn lại kiến thức nào — đặc biệt là không phân biệt được đây là kiến thức cũ (đã học, đang quên) hay kiến thức mới (chưa từng học) — dẫn đến mất 20–30 phút mỗi lần, phần lớn thời gian dành cho việc tìm kiếm lại chứ không phải học.

**Evidence hỗ trợ:** User thực sự bị chặn bởi khái niệm chưa hiểu trong lúc học; mất thời gian tra cứu, giải thích.

**Điều vẫn chưa biết:** Ba cách chia việc user–AI khác nhau (User-led / Collaborative / Proactive) — cách nào giảm thời gian tra cứu mà không làm mất quyền kiểm soát của user.

Chi tiết đầy đủ (bảng so sánh A/B/C, Distance check, Human–AI Decision Table) tại [three-option-design-sheet.md](three-option-design-sheet.md).

---

## 3. Three Solution Options

Cả ba option cùng giải một Hypothesis Problem, cùng target user/situation/task/desired outcome, chỉ khác ở cơ chế Human–AI và ai khởi động tương tác.

| Option                       | Mô tả ngắn                                                                                                                                                                                                                                                 | Prototype                                                   |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| **A — User-led**      | Learner tự khởi tạo: bôi đen đúng đoạn trên slide (select-to-ask), hoặc bấm nút cố định để duyệt danh sách khái niệm quan trọng và tự chọn/mô tả. AI không hành động cho tới khi user xác nhận.                            | [prototype-user-led.html](prototype-user-led.html)           |
| **B — Collaborative** | AI phát hiện dấu hiệu (dừng quá lâu ở một slide) → hỏi xác nhận trước ("Bạn đang gặp vấn đề gì không?") → cùng user xác định đúng khái niệm → đưa nhận xét đã học/chưa học, có nhánh research ngoài bài giảng. | [prototype-collaborative.html](prototype-collaborative.html) |
| **C — Proactive**     | AI phát hiện dấu hiệu → tự tổng hợp và gửi luôn nội dung nghi ngờ user đang thiếu, kèm câu hỏi xác nhận trong cùng một bước → cùng nhánh đã học/chưa học như B.                                                              | [prototype-proactive.html](prototype-proactive.html)         |

Chi tiết trạng thái, trigger giả lập và self-check của từng prototype xem tại [prototype-link.md](prototype-link.md).

---

## 4. Đóng góp của tôi trong nhóm

- **Option phụ trách chính:** Option A
- **Shared context/content:** hỗ trợ chỉnh sửa prototype option B, C; soạn và tổng hợp bài nộp cuối lên github.
- **Human–AI decisions:** Phản biện các quyết định Act/Ask/Don't Act trong Human–AI Decision Table
- **Facilitation:**
- **Observation / tổng hợp feedback:**

---

## 5. Prototype Feedback

### Observation từ phiên tôi facilitate

- Option test: ...
- Tester: ...
- Quan sát chính: ...

### Ba-feedback synthesis

| Practice Note / Feedback | Tester đã làm/nói gì? | Điều nhóm đang diễn giải |
| ------------------------ | -------------------------- | ------------------------------ |
| 1                        | ...                        | ...                            |
| 2                        | ...                        | ...                            |
| 3                        | ...                        | ...                            |

### Next Change

> Với Hypothesis Problem này, chúng tôi đã thử ba cách giải. Tester đã làm..., vì vậy iteration tiếp theo chúng tôi sẽ...

### Still Unproven

- ...

---

## 6. AI Support Log

- **AI đã giúp gì:**

  - Viết code 3 file prototype HTML/CSS/JS ([prototype-user-led.html](prototype-user-led.html), [prototype-collaborative.html](prototype-collaborative.html), [prototype-proactive.html](prototype-proactive.html)) theo đúng luồng tương tác đã mô tả cho từng option.
  - Lặp lại thiết kế theo phản hồi trực tiếp của tôi.
- **AI sai/hời hợt ở đâu:**

  - AI tự đưa ra target user và cơ chế trigger mà không hỏi kỹ, dẫn đến phải sửa lại đúng với ngữ cảnh thực tế .
  - Cơ chế ban đầu của Option A có gợi ý sẵn danh sách khái niệm — đi ngược tinh thần "user-led, không đoán trước" mà nhóm muốn, phải yêu cầu sửa lại thành bôi đen tự do.
- **Tôi tự sửa gì:**

  - Chỉnh sửa lại theo đúng ý tưởng, lọc và lược bỏ các nội dung sai/ không phù hợp.
