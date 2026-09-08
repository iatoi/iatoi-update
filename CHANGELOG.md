# Lịch sử phiên bản

Mô tả đầy đủ từng bản nằm ở [trang phát hành](https://github.com/iatoi/iatoi-update/releases). Dưới đây là bản tóm tắt.

---

## 3.8.4 — Bố mẹ tự mở cửa Cài đặt từ xa
*8/9/2026*

Lớp canh cửa Cài đặt (thêm ở bản 3.8.2) không phân biệt được ai đang cầm máy, nên chặn cả bố mẹ. Muốn chỉnh gì phải cầm máy con lên bấm *Hoàn tất thiết lập* để có 2 phút thao tác.

- **Lệnh mới `/opensettings [phút]`** — mở cửa từ xa, mặc định 10 phút, tối đa 60, tự đóng khi hết giờ. `/opensettings off` đóng ngay.
- `/guard` nay báo cửa đang mở kèm số phút còn lại.

## 3.8.3 — Sửa báo động giả tiếng Việt
*7/9/2026*

Bố mẹ nhận báo động đỏ *"tự tử"* kèm GPS chỉ vì con mở màn hình Cài đặt của một ứng dụng nghe nhạc — hai dòng *"Chính sách Riêng tư"* và *"Tự động cập nhật"* nằm cạnh nhau, bị bỏ dấu rồi đọc thành *"tu tu"*.

- Chữ có dấu mà dấu khác từ nguy hiểm thì bỏ qua; con cố tình gõ không dấu để né thì vẫn bắt được.
- Từ tiếng Anh như *snow*, *ice*, *weed* chỉ tính khi xung quanh có dấu hiệu thật về chất cấm.

## 3.8.2 — Chặn trước, thay vì báo sau
*7/9/2026*

- Chặn con **ngay khi vừa mở** màn hình Trợ năng, Tự khởi động, Chống gỡ, Khôi phục cài đặt gốc — trước đây chỉ báo sau khi việc đã rồi.
- Chặn được cả màn hình Tự khởi động trong Trung tâm bảo mật của Xiaomi.
- Sửa lỗi máy Xiaomi bật *khởi động nhanh* thì IATOI không tự bật lại sau khi tắt/mở máy (lỗi từ bản 3.6.1).
- Lệnh mới `/guard` — xem đủ 5 lớp phòng thủ và lớp nào đang hở.

## 3.8.0 — Riêng tư
*7/9/2026*

- **Sửa lỗi nghiêm trọng:** từ bản 3.7.3, chữ trên màn hình máy con bị gửi ra ngoài cho AI đọc dù cài đặt ghi là chỉ xử lý trên máy. Nay **mặc định tắt hoàn toàn**.
- Lệnh mới `/ai on|off` — bố mẹ toàn quyền quyết định.
- Lệnh mới `/today` — tóm tắt hôm nay con thế nào trong một tin nhắn.
- Lệnh mới `/familylink` — hướng dẫn dùng chung với Google Family Link.
- Giảm mạnh số lần gọi mạng khi quét nội dung, đỡ hao pin.

## 3.7.9 — Sửa lỗi Zalo bị văng
*6/9/2026*

Tính năng chặn kết bạn đá ứng dụng về màn hình chính khi chỉ **nhìn thấy** nút *Thêm bạn*, trong khi trẻ không hề chạm vào. Zalo để nút này thường trực nên bị văng liên tục. Nay chỉ chặn đúng lúc trẻ bấm.

## 3.7.8 — Máy con tự nhận bản cập nhật
*6/9/2026*

Không còn phải gõ `/setupdateurl` bằng tay.

## 3.7.7 — Cảnh báo dễ hiểu hơn
*6/9/2026*

Cảnh báo kèm tóm tắt nội dung; khi còn nghi ngờ thì vẫn gửi để bố mẹ tự xem.

## 3.7.5 — Cảnh báo rõ ràng hơn
*5/9/2026*

Hiển thị tên ứng dụng và ngữ cảnh; sửa báo động giả với từ *snow*.

## 3.7.4 — Sửa lỗi khóa giờ học vào cuối tuần
*5/9/2026*

Giờ học trước đây chạy cả thứ Bảy và Chủ nhật.

## 3.7.3 — Không tự khóa máy con nữa
*5/9/2026*

Thay đổi lớn về cách hoạt động: khi phát hiện nội dung nguy hiểm, IATOI **chụp bằng chứng và báo cho bố mẹ**, quyết định khóa hay không thuộc về bố mẹ. Lý do: máy không hiểu hoàn cảnh, còn lòng tin giữa bố mẹ và con thì khó lấy lại.

## 3.7.1 — Tự chia sẻ hành trình
*5/9/2026*

Tự chia sẻ vị trí trực tiếp 2 khung giờ mỗi ngày, trừ cuối tuần.

## 3.6.1 và trước đó

Xem [danh sách bản phát hành đầy đủ](https://github.com/iatoi/iatoi-update/releases).
