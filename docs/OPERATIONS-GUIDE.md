# EzPrint — Hướng dẫn vận hành

**Phiên bản:** 2.0.4 Experimental · **Đơn vị:** SPXExpress Lâm Đồng

## Trước khi xử lý

- Xác nhận đang dùng đúng tài khoản FMS và đúng Hub.
- Kiểm tra Print Agent đang hoạt động.
- Kiểm tra máy in, khổ giấy và cấu hình trạm.
- Chỉ sử dụng mã đơn thuộc phạm vi được phép xử lý.

## Trong khi tra cứu

- Theo dõi bộ đếm mã hợp lệ và mã bị loại.
- Chờ thông báo hoàn tất trước khi mở quy trình in.
- Kiểm tra trạng thái thực và log nếu nghiệp vụ yêu cầu.
- Không coi tab Pending/Picked up/Pickup On-Hold là trạng thái tracking thực của vận đơn.

## Trước khi xác nhận in

- Kiểm tra từng SPX, nguồn mã và trạng thái.
- Kiểm tra Sortcode/Station theo cấu hình Hub.
- Không gửi nhiều Station ID trong cùng batch nếu extension báo không tương thích.
- Loại bỏ mã không hợp lệ hoặc mã không thuộc batch.

## Sau khi gửi lệnh

- Đối chiếu số dòng được gửi với số dòng phản hồi.
- Kiểm tra kết quả từng mã trong cột Kết quả in.
- Đối với trạng thái chưa rõ Agent đã nhận hay chưa, kiểm tra hàng đợi máy in trước khi retry.
- Đối soát log FMS theo quy trình hiện hành.

## Nguyên tắc an toàn

Không chia sẻ ảnh chụp có dữ liệu khách hàng, tên/email nhân viên, shipment ID thực, token, cookie hoặc URL nhãn có token ở kênh công khai. Khi cần báo lỗi, dùng dữ liệu đã ẩn danh và chỉ gửi qua kênh nội bộ được phép.
