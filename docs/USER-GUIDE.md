# EzPrint — Hướng dẫn sử dụng

**Phiên bản tài liệu:** 2.0.4 Experimental  
**Đơn vị:** SPXExpress Lâm Đồng

> EzPrint đang trong giai đoạn thử nghiệm nội bộ. Chỉ sử dụng trong phạm vi được cấp phép; không tự ý chia sẻ hoặc triển khai tại Hub khác.

## 1. Mục đích

EzPrint hỗ trợ người dùng tra cứu Pickup Task (PT), lấy mã SPX, xem trạng thái và lịch sử tracking, tổng hợp mã hợp lệ và mở cửa sổ xác nhận in AWB.

## 2. Chuẩn bị

- Đăng nhập SPX FMS Portal trong cùng hồ sơ Chrome.
- Mở EzPrint từ Chrome Side Panel.
- Đảm bảo Print Agent được cài đặt và đang chạy nếu cần in.
- Kiểm tra cấu hình máy in/trạm theo hướng dẫn nội bộ.

## 3. Nhập mã và tra cứu

1. Nhập một hoặc nhiều Pickup Task ID và/hoặc SPX Tracking Number.
2. Có thể phân tách mã bằng khoảng trắng hoặc xuống dòng.
3. Kiểm tra bộ đếm PT hợp lệ, SPX nhận diện, trùng và nội dung nhiễu.
4. Nhấn **Tra cứu** và đợi hệ thống hoàn tất.
5. Kiểm tra từng Task và danh sách SPX trả về.

PT là khóa tra cứu Task, không phải shipment ID gửi tới quy trình in. SPX nhập trực tiếp là nguồn độc lập và vẫn được xét vào danh sách nếu hợp lệ.

## 4. Đọc trạng thái và log

- Mỗi PT có các tab Pending, Picked up và Pickup On-Hold.
- Tab đang chọn quyết định tập đơn API hiển thị cho PT đó.
- Trạng thái vận đơn và lịch sử tracking được lấy từ API FMS.
- Dùng **View Log** để xem sự kiện, thời gian và thông tin thao tác được FMS trả về.
- Nếu không xác minh được trạng thái, không tự suy đoán tên trạng thái.

## 5. Chuẩn bị và xác nhận in

1. Nhấn **In nhãn SPX**.
2. Kiểm tra mã PT, mã SPX, nguồn mã, trạng thái, Sortcode, ETA và kết quả in.
3. Xác nhận chỉ chọn các dòng thuộc cùng một Station/Hub theo quy định vận hành.
4. Kiểm tra số bản in và cấu hình trạm.
5. Có thể xem nhãn trước bằng **Xem nhãn**.
6. Chỉ nhấn **Xác nhận in** sau khi đã kiểm tra danh sách.

Print Agent trả lời nhận request không đồng nghĩa giấy đã được in vật lý. Cần kiểm tra hàng đợi máy in và bản ghi hệ thống theo quy trình của đơn vị.

## 6. Xử lý tình huống

- **Không có dữ liệu:** kiểm tra mã PT/SPX, quyền truy cập và phiên FMS.
- **Không có trạng thái:** thực hiện tra cứu lại; không tự gán trạng thái.
- **Print Agent lỗi:** kiểm tra Agent, kết nối và cấu hình máy in.
- **Kết quả gửi không rõ:** kiểm tra hàng đợi trước khi gửi lại để tránh in trùng.
- **Mã sai định dạng:** không cố in; loại bỏ và nhập lại mã chính xác.

## 7. Báo lỗi

Khi báo lỗi, cung cấp thời điểm, thao tác vừa thực hiện, thông báo lỗi và mã mẫu đã được phép chia sẻ. Không gửi mật khẩu, cookie, token, URL nhãn có token hoặc HAR chứa thông tin xác thực.

## 8. Giới hạn

EzPrint v2.0.4 Experimental là công cụ hỗ trợ thử nghiệm; dữ liệu FMS là nguồn tham chiếu chính. Người vận hành vẫn phải thực hiện kiểm soát nghiệp vụ và đối soát kết quả.
