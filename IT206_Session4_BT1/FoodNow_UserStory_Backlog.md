# Rà soát User Story và sắp xếp Product Backlog – FoodNow

## Bước 1. Tìm lỗi (INVEST)

| Mã | Kết quả và lý do |
|----|------------------|
| US1 | **Đạt**: vai trò rõ, một việc, có lợi ích, thử được bằng cách chọn loại món rồi xem kết quả. |
| US2 | **Sai T (Testable)**: "đẹp và dễ dùng" mang tính cảm nhận, không có tiêu chí đo được nên không biết khi nào là xong (kéo theo khó ước lượng – E). |
| US3 | **Sai V (Valuable)**: đây là việc kỹ thuật/giải pháp ("dùng React") phục vụ lập trình viên, không mang lại giá trị cho người dùng cuối; nó cũng áp đặt cách làm nên vi phạm N (Negotiable). Việc kỹ thuật vẫn có thể nằm trong backlog nhưng nên ghi là Technical Task/Enabler gắn với một story có giá trị cho khách hàng, không viết dưới dạng User Story. |
| US4 | **Sai S (Small)**: gộp quá nhiều việc (xem theo ngày/tuần/tháng, theo khu vực, theo nhà hàng, xuất Excel, tự gửi email) nên không vừa một Sprint và không ước lượng được (kéo theo sai E). |

## Bước 2. Sửa lỗi

### a) Viết lại US2 với tiêu chí "dễ dùng" đo được

**US2 (viết lại):** Là một khách hàng, tôi muốn hoàn tất việc đặt món từ giỏ hàng đến màn hình xác nhận chỉ trong tối đa 3 màn hình, để đặt món nhanh và ít nhầm lẫn.

**Tiêu chí chấp nhận:**
- Given giỏ hàng đã có món, When khách bấm "Đặt món", Then khách hoàn tất đơn qua tối đa 3 màn hình (giỏ hàng → địa chỉ & thanh toán → xác nhận).
- Khi thử nghiệm với 5 người dùng mới, ít nhất 4 người đặt xong 1 đơn trong vòng 60 giây mà không cần hướng dẫn.

### b) Tách US4 và đặt vào cây Epic → Feature → Story

```
Epic: Báo cáo & phân tích kinh doanh
└── Feature: Báo cáo doanh thu
    ├── US4a: Là một admin, tôi muốn xem tổng doanh thu theo ngày (chọn ngày bất kỳ),
    │         để theo dõi tình hình kinh doanh hằng ngày.
    └── US4b: Là một admin, tôi muốn xuất báo cáo doanh thu theo ngày ra file Excel,
              để lưu trữ và chia sẻ với ban giám đốc.
```

Các phần còn lại của US4 gốc (xem theo tuần/tháng, theo khu vực, theo nhà hàng, tự gửi email) được giữ lại thành các story riêng, ưu tiên thấp, sẽ tách chi tiết ở các buổi Refinement sau.

## Bước 3. Xếp lại backlog

### a) Thứ tự ưu tiên

| Thứ tự | Story | Lý do |
|--------|-------|-------|
| 1 | US1 – Lọc nhà hàng theo loại món | Đạt INVEST, nhỏ, sẵn sàng làm ngay; giúp khách tìm món nhanh, là giá trị trực tiếp cho người dùng cuối. |
| 2 | US2 (đã sửa) – Đặt món tối đa 3 màn hình | Thuộc luồng đặt món cốt lõi, ảnh hưởng trực tiếp đến doanh thu và cam kết giao trong 30 phút; đã có tiêu chí đo được nhưng cần thêm chi tiết nên đứng sau US1. |
| 3 | US4a – Xem doanh thu theo ngày | Giá trị cho vận hành, nhưng chỉ có ý nghĩa khi đã có đơn hàng; ưu tiên sau các story hướng tới khách hàng. |
| 4 | US4b – Xuất báo cáo ra Excel | Phụ thuộc vào US4a (cần có báo cáo trước khi xuất), giá trị tiện ích hơn là cốt lõi. |

### b) Theo DEEP

**Story đứng đầu cần chi tiết đến mức nào?**
Theo DEEP (Detailed appropriately), phần đầu backlog phải chi tiết nhất: story nhỏ vừa một Sprint, có tiêu chí chấp nhận rõ ràng (Given–When–Then), phạm vi và các trường hợp biên đã được làm rõ, có thể kèm wireframe/mẫu giao diện, không còn câu hỏi mở và đã sẵn sàng để ước lượng. Các story ở cuối backlog thì chỉ cần mô tả thô (nguyên tắc Emergent: càng gần thời điểm làm càng chi tiết).

**Buổi Refinement còn phải làm gì với nó trước khi đưa vào Sprint?**
- Làm rõ yêu cầu và các câu hỏi còn mở với Product Owner.
- Viết/chốt tiêu chí chấp nhận.
- Ước lượng (Estimated), ví dụ bằng Planning Poker; nếu vượt quá một Sprint thì tách nhỏ tiếp.
- Rà lại INVEST và xác định phụ thuộc, đối chiếu với Definition of Ready.
- Xác nhận thứ tự ưu tiên (Prioritized) với Product Owner. Sau đó, story mới được nhóm kéo vào Sprint ở buổi Sprint Planning.
