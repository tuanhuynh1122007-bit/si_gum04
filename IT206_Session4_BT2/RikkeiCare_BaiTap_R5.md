# Bài tập: User Story, Acceptance Criteria và theo dõi trên Trello (RikkeiCare)

**Yêu cầu xử lý:** R5 - Phòng khám tự cập nhật giá các gói khám

---

## Bước 1. User Story cho R5

> **Là một** quản lý phòng khám, **tôi muốn** tự cập nhật giá các gói khám của phòng khám mình, **để** bảng giá trên ứng dụng luôn đúng và không phải chờ admin RikkeiCare cập nhật hộ qua email.

**Vì sao chọn vai trò "quản lý phòng khám" mà không phải "admin RikkeiCare"?**

1. **Người có nhu cầu và người thực hiện hành động là quản lý phòng khám.** Họ là người biết giá mới, muốn đổi giá và hưởng lợi khi giá được cập nhật nhanh. Vai trò trong User Story phải là người dùng thật sự cần và dùng chức năng.
2. **Admin chỉ là khâu trung gian, là cách làm tạm.** Việc admin cập nhật hộ qua email chính là vấn đề cần giải quyết (chậm, dễ sai, phụ thuộc người). Nếu viết story theo admin thì ta đang thiết kế để củng cố cách làm cũ thay vì loại bỏ nó.
3. **Vế "So that" mới có lợi ích rõ ràng.** Với quản lý phòng khám, lợi ích là giá luôn đúng và không phải chờ đợi. Với admin thì lợi ích mơ hồ hơn.
4. Nếu sau này admin cần xem hoặc kiểm tra lịch sử đổi giá, đó là **một User Story khác**, không gộp vào story này (giữ story nhỏ theo INVEST).

---

## Bước 2. Phần "Then" cho 2 Acceptance Criteria

**AC 1 (thành công)**
- **Given** quản lý phòng khám đã đăng nhập,
- **When** nhập giá mới cho một gói khám rồi nhấn "Lưu",
- **Then** hệ thống lưu giá mới, hiển thị thông báo "Cập nhật giá thành công", và giá mới của gói khám đó hiển thị cho bệnh nhân trên ứng dụng từ lần xem tiếp theo (giá cũ không còn hiển thị).

**AC 2 (thất bại)**
- **Given** quản lý để trống ô giá,
- **When** nhấn "Lưu",
- **Then** hệ thống **không lưu**, giữ nguyên giá cũ, và hiển thị lỗi "Vui lòng nhập giá" ngay dưới ô giá.

*Ghi chú:* các Then trên đều kiểm thử được (có thông báo cụ thể, có kết quả nhìn thấy được), để Tester biết thử thế nào.

---

## Bước 3. Thẻ R5 kéo sang "Ready for Sprint" được chưa?

**Trả lời: Chưa được.**

| Điều kiện trong Definition of Ready | Thẻ R5 hiện tại | Đạt? |
|---|---|---|
| Có User Story đủ 3 vế (Role, Action, Value) | Đã viết ở Bước 1 | Đạt |
| Có tiêu chí nghiệm thu | Đã có 2 AC ở Bước 2 | Đạt |
| Đã được ước lượng | Chưa có Story Points nào được Developers đưa ra | **Chưa đạt** |
| Đủ nhỏ để làm xong trong 1 Sprint | Chưa thể kết luận khi chưa ước lượng | **Chưa xác định** |

**Vì sao:** Definition of Ready yêu cầu đạt **đủ cả 4 điều kiện**. Mới có 2/4. Việc ước lượng do **Developers** thực hiện (ví dụ Planning Poker trong buổi Backlog Refinement), không phải PO tự quyết. Chưa ước lượng thì cũng không biết thẻ có đủ nhỏ cho một Sprint hay không.

**Cần làm trước khi kéo sang:** Developers ước lượng R5 (đề cho biết sau đó R5 là 3 point, tức là đủ nhỏ), ghi Story Points lên thẻ. Khi cả 4 điều kiện đạt thì PO mới kéo sang "Ready for Sprint".

---

## Bước 4. Hoàn thiện thẻ R5 trên Trello

| Mục | Nội dung |
|---|---|
| **Tên thẻ** | R5 - Quản lý phòng khám tự cập nhật giá gói khám (3) |
| **Nhãn (Label)** | **Xanh dương (Feature)** |
| **Người phụ trách (Member)** | [Tên Developer được giao] |
| **Hạn hoàn thành (Due date)** | Ngày 8 của Sprint (còn 2 ngày để Review/QA và demo) |
| **Cột** | Sprint Backlog |
| **Vị trí trong cột** | **Trên cùng (đầu cột)** |

**Description của thẻ:** dán User Story (Bước 1) và 2 AC (Bước 2).

**Checklist (3 mục):**
- [ ] Làm form nhập giá gói khám, kiểm tra ô trống
- [ ] Làm chức năng lưu giá và cập nhật giá hiển thị cho bệnh nhân
- [ ] Viết và chạy test case theo 2 AC

**Giải thích:**
- **Nhãn xanh dương:** R5 là chức năng mới. Không phải Bug (chưa có gì hỏng), không phải Technical debt, không phải Epic (chỉ 3 point, đủ nhỏ).
- **Hạn ngày 8:** Sprint dài 10 ngày. Đặt hạn trước ngày cuối để còn thời gian cho QA và Sprint Review, tránh dồn việc cuối Sprint.
- **Đặt ở đầu cột:** trong Trello, thứ tự từ trên xuống thể hiện mức ưu tiên. R5 ưu tiên cao nhất nên nằm trên cùng.

---

## Bước 5. Đọc Burndown Chart

Đường lý tưởng: giảm 3 point mỗi ngày từ 30 point.

| Ngày | 0 | 2 | 4 | 6 |
|---|---|---|---|---|
| Lý tưởng | 30 | 24 | 18 | 12 |
| Thực tế | 30 | 26 | 23 | 20 |
| Chênh lệch | 0 | +2 | +5 | **+8** |

### a) Ngày 6 nhóm nhanh hay chậm?

**Nhóm đang CHẬM.** Ngày 6 đường lý tưởng là 30 - 3 x 6 = **12 point**, nhưng thực tế còn **20 point**, nghĩa là chậm **8 point** (còn nhiều việc hơn kế hoạch 8 point).

**Nhận xét thêm:**
- Độ trễ đang **tăng dần** (2, 5, rồi 8 point), không phải trễ ổn định.
- Tốc độ thực tế khoảng (30 - 20) / 6 ≈ **1,7 point mỗi ngày**, thấp hơn nhiều so với 3 point mỗi ngày. Nếu giữ nguyên, đến ngày 10 vẫn còn khoảng 13 point chưa xong, tức là **không đạt cam kết 30 point**.
- Hành động: nêu ngay ở Daily Scrum, Scrum Master tìm và gỡ rào cản, PO cùng Developers thương lượng bỏ bớt item ưu tiên thấp để bảo vệ Sprint Goal. Không kéo dài Sprint.

### b) Có nên trừ 3 point khi bạn báo thẻ R5 "xong 80%" không?

**Không nên.**

1. Burndown chỉ trừ point khi thẻ **hoàn thành hoàn toàn (Done)**, tức đạt Definition of Done: code xong, qua QA, đáp ứng đủ AC và PO chấp nhận. "Xong 80%" nghĩa là **chưa có Increment dùng được**.
2. Trừ điểm cho việc chưa xong làm biểu đồ **đẹp giả**: nhìn tưởng nhanh hơn thực tế. Điều này làm mất tính **minh bạch** (Transparency), một trụ cột của Scrum, và che mất rủi ro trễ hạn.
3. Phần "80%" khó kiểm chứng. Phần 20% còn lại (test, sửa lỗi, review) thường chiếm nhiều thời gian hơn dự đoán.

**Cách làm đúng:** giữ nguyên 3 point cho đến khi thẻ chuyển sang **Done**. Nếu muốn thể hiện tiến độ, dùng **checklist** trên thẻ (hoặc chia thẻ thành các story nhỏ hơn để hoàn thành sớm và trừ điểm từng phần).
