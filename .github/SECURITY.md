# Báo lỗi bảo mật

IATOI chạy trên điện thoại của trẻ em và có quyền đọc nội dung màn hình. Một lỗ hổng ở đây ảnh hưởng trực tiếp tới sự an toàn và riêng tư của một đứa trẻ. Chúng tôi xem mọi báo cáo bảo mật là việc ưu tiên.

## Phiên bản được hỗ trợ

Chỉ bản mới nhất trên [trang phát hành](https://github.com/iatoi/iatoi-update/releases/latest). Bản cũ không nhận bản vá — vui lòng cập nhật trước khi báo lỗi.

## Cách báo

**Đừng mở phiếu công khai cho lỗ hổng bảo mật.** Mở phiếu công khai nghĩa là ai đọc được cũng biết cách khai thác, trong khi bản vá chưa có.

Dùng đường riêng tư của GitHub: **[Báo lỗ hổng bảo mật](https://github.com/iatoi/iatoi-update/security/advisories/new)** — chỉ chúng tôi đọc được.

Nội dung nên có: mô tả lỗ hổng · cách tái hiện · phiên bản IATOI và đời máy · hậu quả nếu bị khai thác.

## Cam kết

- Phản hồi trong vòng **7 ngày**.
- Lỗ hổng nghiêm trọng (rò dữ liệu trẻ, chiếm quyền điều khiển) được vá và phát hành trước mọi việc khác.
- Bản vá đi kèm ghi chú thành thật về chuyện đã xảy ra, không giấu.

## Ngoài phạm vi

- **Safe Mode gỡ được lá chắn** — đã biết và ghi rõ trong [README](../README.md#hỏi-đáp). Android không cho ứng dụng thường chặn Safe Mode.
- **Trẻ tắt Trợ năng khi ứng dụng chưa kịp chặn** — Android không cho ứng dụng tự bật lại quyền của chính nó.
- Tấn công cần mở khóa máy con và có sẵn quyền quản trị.

## Một điều xin nhắc

Nếu bạn dán nhật ký (`/diag`, log hệ thống) vào báo cáo, **hãy xóa Token bot Telegram**. Token lộ ra là người khác điều khiển được máy con.
