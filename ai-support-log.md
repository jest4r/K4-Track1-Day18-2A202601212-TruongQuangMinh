# AI Support Log — Day 18

| Thông tin             | Nội dung                                                                                          |
| ---------------------- | -------------------------------------------------------------------------------------------------- |
| **MHV**          | 2A202601212                                                                                        |
| **Họ và tên** | Trương Quang Minh                                                                                |
| **Nhóm**        | MT                                                                                                 |
| **Case**         | Case A — AI Tutor: Diagnostic Refresher                                                           |
| **Phạm vi log** | Research 3 solution options → dựng 3 micro-prototype → iterate theo feedback (đến 19/08/2026) |

---

## 1. AI đã giúp gì

### 1.1. Research và định hình 3 hướng solution options

- Giúp tìm ra **trục phân biệt** cho ba option thay vì ba biến thể UI của cùng một cơ chế: ai khởi động tương tác và AI được phép hành động tới đâu — `A: USER INITIATES → B: USER + AI CO-CREATE → C: AI INITIATES, USER REVIEWS`.
- Dựng bộ khung so sánh A/B/C trong [three-option-design-sheet.md](three-option-design-sheet.md): solution mechanism, user làm gì / AI làm gì, trigger, trade-off chính.
- Viết nháp **Distance check** (A khác B / B khác C / A khác C) và **Human–AI Decision Table** với cột Act / Ask / Don't Act, tôi phản biện lại từng quyết định trên bảng này.
- Giữ chung Target user / Situation / Task / Desired outcome / content fixture cho cả ba option, để ba prototype thật sự so sánh được với nhau khi test.

### 1.2. Dựng 3 prototype chạy được

- Viết code HTML/CSS/JS cho ba file, mỗi file một luồng tương tác khác nhau nhưng dùng chung một slide làm common context:
  - [prototype-user-led.html](prototype-user-led.html) — select-to-ask (bôi đen → nút nổi) + nút cố định để duyệt khái niệm.
  - [prototype-collaborative.html](prototype-collaborative.html) — AI hỏi xác nhận trước khi hành động.
  - [prototype-proactive.html](prototype-proactive.html) — AI tự tổng hợp và gửi luôn, hỏi xác nhận trong cùng một bước.
- Làm nút **giả lập trigger** (`⏱ Giả lập: đã xem slide >15 phút`) cho B/C để test được ngay mà không phải chờ thật.
- Giữ slide luôn hiển thị, mọi bước hội thoại nối tiếp nhau ở panel bên phải — không đổi màn hình, không che nội dung đang học.

### 1.3. Sửa prototype theo feedback sau khi test

Sau khi có đủ ba feedback ([GroupFeedbackSynthesis.md](GroupFeedbackSynthesis.md)), AI thực hiện các sửa đổi tôi yêu cầu:

- **Đổi nhánh cuối của B/C:** từ "đã học / chưa học" (phân loại kiến thức) sang **"đã hiểu / chưa hiểu"** — nếu chưa hiểu thì vòng hỏi–đáp quay lại tiếp tục, đúng với hành vi thật của tester là hỏi thêm cho tới khi hiểu.
- **Siết ô chat:** textarea bị `disabled`, chỉ mở khi user chọn "Khác" — trước đó user có thể vừa chọn chip vừa gõ, làm nhiễu tín hiệu test.
- **Thêm nhánh off-topic:** nếu câu tự mô tả không khớp nội dung bài giảng (`isRelatedToCourse`), AI hỏi có muốn tìm kiếm bên ngoài không thay vì trả lời bừa như thể có trong bài.
- **Đồng bộ lại giao diện cả ba file:** design token, typography, sidebar dạng hành trình từng bước, trạng thái focus/hover, `prefers-reduced-motion`.

---

## 2. AI sai / hời hợt ở đâu

### 2.1. Hời hợt ở khâu xác nhận với người dùng

- AI **tự quyết định** target user, situation và cơ chế trigger rồi code luôn, không hỏi lại tôi một câu nào, dẫn đến prototype lệch khỏi ngữ cảnh thực tế mà nhóm đang nhắm tới, phải sửa lại.
- Option A ban đầu **gợi ý sẵn danh sách khái niệm** cho user chọn. Điều này đi ngược đúng tinh thần của option: user-led là user tự chỉ ra chỗ mình không hiểu, AI không đoán trước. Tôi phải yêu cầu làm lại thành bôi đen tự do.
- Nghịch lý là AI mắc đúng lỗi mà nhóm đang test: chọn **Act** ở những quyết định mà lẽ ra phải **Ask** — trong khi bảng Human–AI Decision Table do chính nó soạn nháp lại ghi rõ "Ask trước khi Act vì chẩn đoán có thể sai".

### 2.2. Hời hợt ở khâu tìm kiếm thông tin

- Nội dung học liệu AI tự chọn là **một bài toán lớp 9** ("Đường thẳng và hệ số góc", `y = ax + b`, hệ số góc, hai đường song song) — không liên quan gì đến bối cảnh khoá học, nên không test được đúng vấn đề mà Hypothesis Problem đang nói tới.
- Phần "nguồn tham khảo" trong nhánh research ngoài bài giảng là **nguồn bịa/mock** (`Khan Academy — Slope of a line (mock link)`, `SGK Toán 9, chương 2`). AI không đi tìm nguồn thật, cũng không chủ động nói rõ đây chỉ là placeholder cho tới khi tôi hỏi.
- Ba đoạn giải thích khái niệm (`conceptExplanations`) vì thế cũng là nội dung tự sinh, không dựa trên tài liệu nào.

---

## 3. Tôi tự sửa / tự làm gì

- **Tự research nguồn uy tín** và thay toàn bộ fixture nội dung: dùng nội dung Product Discovery của khoá và **The Mom Test (Rob Fitzpatrick)** làm slide thật — "Evidence mạnh và tín hiệu yếu nghe rất khác nhau", chuỗi **Event → Behavior → Workaround → Consequence**, hai lý do câu trả lời dễ nghe không phải evidence (trả lời cho lịch sự / ai cũng muốn cái tốt hơn), nguyên tắc hỏi về một lần đã xảy ra thay vì hỏi giả định tương lai.
- **Viết lại ba khái niệm trong danh sách chọn** và phần giải thích tương ứng (`event-behavior`, `tra-loi-lich-su`, `hoi-qua-khu`) cho khớp nội dung thật, thay ba khái niệm toán học.
- **Chốt lại cơ chế cho đúng ý tưởng ban đầu:** A không được gợi ý trước, chỉ bôi đen tự do; B bắt buộc hỏi xác nhận trước khi hành động; chỉ C mới được tự đưa nội dung trước.
- **Lọc và lược bỏ** những nội dung AI tự thêm ngoài phạm vi hoặc không đúng ý tưởng.
- **Tự chạy lại từng bước luồng của cả ba file** (bôi đen, giả lập trigger, chọn Có/Không, nhánh off-topic, vòng "chưa hiểu") trước khi nộp.
