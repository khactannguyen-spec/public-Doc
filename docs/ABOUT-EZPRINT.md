# Giới thiệu EzPrint

EzPrint là tiện ích Chrome nội bộ dạng Manifest V3 dành cho quy trình tra cứu Pickup Task và SPX Tracking Number, hiển thị trạng thái/tracking log, tổng hợp mã SPX hợp lệ và hỗ trợ in AWB.

## Phạm vi chức năng

- Tra cứu nhiều PT và SPX trong Side Panel.
- Hiển thị danh sách đơn theo các tab trạng thái Pickup Task độc lập.
- Lấy trạng thái vận đơn và lịch sử tracking từ API FMS.
- Hợp nhất mã SPX từ kết quả API và nhập trực tiếp, loại trùng.
- Mở cửa sổ xác nhận, xem nhãn và gửi yêu cầu in qua WMS Print Agent.

## Phạm vi sử dụng

EzPrint v2.0.4 Experimental được chuẩn bị cho thử nghiệm nội bộ tại SPXExpress Lâm Đồng. Không phải sản phẩm công khai dành cho khách hàng hoặc công cụ thay thế toàn bộ FMS. Việc dùng công cụ phải tuân theo quyền truy cập và quy trình vận hành hiện hành.

## Giới hạn quan trọng

- Trạng thái và dữ liệu vận đơn phụ thuộc phản hồi API FMS và quyền của tài khoản.
- Print Agent nhận request không chứng minh giấy đã in.
- Một số chức năng có thể thay đổi trong các bản thử nghiệm.
- Không sử dụng dữ liệu nhạy cảm hoặc phiên đăng nhập trong tài liệu công khai.
