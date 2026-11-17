# EzPrint — Hướng dẫn thử nghiệm

**Phiên bản:** 2.0.4 Experimental

## Phạm vi

Tài liệu này dành cho thử nghiệm nội bộ được phê duyệt. Dùng mã test hoặc mã nghiệp vụ đã được người vận hành cho phép; không tạo lệnh in vật lý ngoài kế hoạch.

## Ma trận kiểm thử

| ID | Tình huống | Kết quả mong đợi |
|---|---|---|
| T01 | PT hợp lệ | Nhận diện và tra cứu được |
| T02 | SPX hợp lệ nhập trực tiếp | Được tra cứu độc lập |
| T03 | SPX trùng từ API và nhập tay | Một dòng canonical, giữ nguồn |
| T04 | Chuỗi giả như SPX hoặc SPXVN thiếu ký tự | Không được gửi in |
| T05 | Nội dung nhiễu trong ô nhập | Bỏ qua, không tạo shipment |
| T06 | Chuyển tab trạng thái của một PT | Chỉ tập API của PT đó thay đổi |
| T07 | API tracking lỗi | Hiển thị lỗi xác minh, không tự gán trạng thái |
| T08 | Mã trạng thái chưa có trong cache | Yêu cầu tra cứu bổ sung theo thiết kế |
| T09 | Nhiều Station ID trong cùng batch | Chặn batch không hợp lệ |
| T10 | Print Agent từ chối request | Hiển thị lỗi riêng dòng |
| T11 | Agent timeout/không rõ kết quả | Đánh dấu chưa rõ; kiểm tra hàng đợi trước retry |
| T12 | Agent nhận request | Chỉ ghi nhận đã nhận request, không khẳng định giấy đã in |

## Quy trình ghi nhận lỗi

Mỗi lỗi cần ghi:
- Mã test và thời điểm.
- Phiên bản extension, phiên bản Chrome.
- Các bước tái hiện.
- Kết quả mong đợi và kết quả thực tế.
- Ảnh chụp đã ẩn danh.
- Mã lỗi/HTTP status nếu có.

Không đưa HAR nguyên bản, cookie, authorization header, token, email nhân viên hoặc dữ liệu vận đơn thật lên kho tài liệu công khai.

## Tiêu chí hoàn tất

- Không có mã giả lọt vào print set.
- Copy và Print sử dụng cùng canonical SPX set.
- Trạng thái thực không bị thay bằng tab Pickup Task.
- Kết quả Agent và trạng thái in vật lý được phân biệt.
- Lỗi của một mã không chặn các mã hợp lệ khác nếu thiết kế cho phép xử lý riêng.
