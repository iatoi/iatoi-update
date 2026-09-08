# CHÍNH SÁCH BẢO MẬT — IATOI Parental Control
> Cập nhật: 2026-09-08 · Áp dụng cho bản 3.8.4 trở đi

## 1. GIỚI THIỆU
IATOI Parental Control ("Ứng dụng", "chúng tôi") là ứng dụng kiểm soát của phụ huynh dành cho thiết bị Android. Ứng dụng được thiết kế để giúp phụ huynh giám sát và bảo vệ con em mình trên không gian mạng.

**Nguyên tắc cốt lõi:** IATOI xử lý **trên thiết bị**. Chúng tôi **KHÔNG vận hành máy chủ backend** và **KHÔNG thu thập dữ liệu về máy chủ của chúng tôi**. Dữ liệu được lưu cục bộ trên máy con và chỉ truyền đến phụ huynh qua Bot Telegram **DO CHÍNH PHỤ HUYNH TẠO VÀ SỞ HỮU**.

**Một ngoại lệ duy nhất, do phụ huynh tự bật:** ứng dụng có tính năng nhờ AI đọc giúp những đoạn nội dung khó phân định. Tính năng này **MẶC ĐỊNH TẮT**; khi tắt, không một chữ nào rời khỏi máy con. Xem [mục 2A](#2a-ai-đám-mây--tùy-chọn-mặc-định-tắt) để biết chính xác điều gì xảy ra khi bật.

## 2. DỮ LIỆU ĐƯỢC THU THẬP & LƯU TRỮ

Ứng dụng thu thập và lưu trữ **TRÊN THIẾT BỊ** các loại dữ liệu sau:

| Loại dữ liệu | Mục đích | Lưu ở đâu |
|---|---|---|
| **Bot Token Telegram** | Kết nối với Bot do phụ huynh tạo để nhận lệnh | Thiết bị (mã hóa AES-256) |
| **Chat ID Telegram** | Định danh phụ huynh để gửi cảnh báo | Thiết bị |
| **Nội dung hiển thị trên màn hình** | Quét từ khóa nguy hiểm (tự tử, bạo lực, ma túy...) | Chỉ xử lý tạm thời, không lưu |
| **Danh sách ứng dụng đã cài** | Quản lý app bị chặn/cho phép | Thiết bị |
| **Thời gian sử dụng ứng dụng** | Báo cáo thời gian dùng app cho phụ huynh | Thiết bị |
| **Vị trí GPS** | Định vị khi phụ huynh yêu cầu hoặc định kỳ | Thiết bị |
| **Ảnh chụp màn hình** | Gửi bằng chứng khi phát hiện nội dung nguy hiểm | Tạo tạm thời, gửi rồi xóa |

## 2A. AI ĐÁM MÂY — TÙY CHỌN, MẶC ĐỊNH TẮT

Bộ từ điển tiếng Việt chạy trên máy đôi khi không đủ để phân định một đoạn chữ là nguy hiểm thật hay vô hại. IATOI có tùy chọn gửi đoạn chữ đó tới một dịch vụ AI để hỏi ý kiến.

**Trạng thái mặc định là TẮT.** Khi tắt, không một chữ nào trên màn hình máy con rời khỏi thiết bị.

| | Khi TẮT (mặc định) | Khi phụ huynh BẬT |
|---|---|---|
| Chữ trên màn hình con | Chỉ xử lý trên máy | Đoạn chữ nghi vấn được gửi đi để phân loại |
| Ảnh chụp màn hình | Không gửi | Không gửi |
| Vị trí, danh bạ, tin nhắn | Không gửi | Không gửi |
| Danh tính của trẻ | Không gửi | Không gửi (chỉ gửi đoạn chữ, không kèm tên, số máy hay mã thiết bị) |

**Cách bật/tắt và kiểm tra:**

- `/ai off` — tắt (trạng thái mặc định)
- `/ai on` — bật
- `/diag` — xem hiện đang bật hay tắt

**Các hạn chế áp dụng khi bật:** chỉ gửi khi bộ từ điển trên máy không tự kết luận được; không gửi lại nội dung trùng; giới hạn số lần gọi; mỗi lúc chỉ một yêu cầu đang chờ.

**Lịch sử minh bạch:** từ bản 3.7.3 đến 3.7.9, do một lỗi lập trình, tính năng này chạy **kể cả khi phần cài đặt ghi là chỉ xử lý trên máy**. Lỗi được phát hiện và sửa ở bản **3.8.0**, kể từ đó mặc định là tắt hoàn toàn và phụ huynh có toàn quyền quyết định. Chúng tôi ghi lại chuyện này ở đây thay vì bỏ qua.

---

## 3. DỮ LIỆU ĐƯỢC CHIA SẺ

Dữ liệu được **gửi đến phụ huynh** qua Telegram Bot API (`api.telegram.org`):
- Cảnh báo từ khóa nguy hiểm (kèm ảnh chụp màn hình + vị trí GPS)
- Báo cáo thời gian sử dụng ứng dụng
- Vị trí GPS khi phụ huynh yêu cầu
- Trạng thái thiết bị (online/offline, pin, cảnh báo cài app mới)

Với cài đặt mặc định, **Telegram là bên thứ ba duy nhất** nhận dữ liệu. Bot Telegram do chính phụ huynh tạo và sở hữu — chúng tôi không có quyền truy cập vào Bot hoặc dữ liệu truyền qua đó.

Nếu phụ huynh **tự bật** tính năng AI ở [mục 2A](#2a-ai-đám-mây--tùy-chọn-mặc-định-tắt), dịch vụ AI là bên thứ ba thứ hai, và chỉ nhận đoạn chữ nghi vấn.

Chúng tôi **KHÔNG**:
- Gửi dữ liệu đến máy chủ của chúng tôi (không có backend)
- Bán hoặc chia sẻ dữ liệu cho bên thứ ba khác
- Sử dụng dữ liệu cho mục đích quảng cáo

## 4. QUYỀN TRUY CẬP

| Quyền | Lý do |
|---|---|
| **Accessibility Service (Trợ năng)** | Quét nội dung màn hình để phát hiện từ khóa nguy hiểm; chặn nút kết bạn trên mạng xã hội; cưỡng chế giới hạn thời gian |
| **Vị trí (GPS)** | Định vị thiết bị khi phụ huynh yêu cầu (`/location`) hoặc định kỳ (`/trackgps`) |
| **Usage Access (Truy cập sử dụng)** | Đọc thời gian dùng app để báo cáo và cưỡng chế giới hạn thời gian |
| **Device Admin** | Chống gỡ cài đặt ứng dụng (yêu cầu xác nhận của phụ huynh) |
| **Thông báo (Foreground Service)** | Hiển thị thông báo thường trực "thiết bị đang được phụ huynh giám sát" (minh bạch) |
| **QUERY_ALL_PACKAGES** | Liệt kê ứng dụng đã cài để phụ huynh quản lý (chặn/cho phép) |
| **Boot Completed** | Tự khởi động lại dịch vụ giám sát sau khi khởi động lại máy |

## 5. BẢO MẬT DỮ LIỆU

- **Bot Token** được mã hóa AES-256/GCM sử dụng Android Keystore (hardware-backed nếu thiết bị hỗ trợ).
- Dữ liệu lưu trữ cục bộ trong thư mục riêng của ứng dụng (không ứng dụng nào khác truy cập được).
- Kết nối đến Telegram API qua HTTPS (mã hóa TLS).
- Ứng dụng có cơ chế **PIN phụ huynh** để ngăn trẻ thay đổi cấu hình.

## 6. QUYỀN CỦA NGƯỜI DÙNG

- **Xóa dữ liệu:** Gỡ cài đặt ứng dụng sẽ xóa toàn bộ dữ liệu cục bộ. Dữ liệu đã gửi qua Telegram nằm trong lịch sử chat của phụ huynh — phụ huynh có thể xóa thủ công.
- **Ngừng giám sát:** Tắt Accessibility Service cho IATOI trong Cài đặt > Trợ năng.
- **Tắt Device Admin:** Vào Cài đặt > Bảo mật > Quản trị viên thiết bị > bỏ chọn IATOI, sau đó gỡ cài đặt.

## 7. TRẺ EM

Ứng dụng được thiết kế để phụ huynh cài đặt và quản lý thiết bị của con. Phụ huynh chịu trách nhiệm:
- Có sự đồng ý hợp pháp để giám sát thiết bị của trẻ
- Tuân thủ luật pháp địa phương về giám sát trẻ em
- Ứng dụng hiển thị màn hình **ĐỒNG Ý (consent)** minh bạch khi cài đặt lần đầu

## 8. TUÂN THỦ PHÁP LUẬT VIỆT NAM

Ứng dụng tuân thủ **Nghị định 13/2023/NĐ-CP** về bảo vệ dữ liệu cá nhân:
- Dữ liệu được xử lý trên thiết bị, không chuyển ra nước ngoài (trừ Telegram - bên thứ ba do phụ huynh lựa chọn)
- Có sự đồng ý minh bạch trước khi xử lý dữ liệu
- Phụ huynh có quyền truy cập, chỉnh sửa, xóa dữ liệu

## 9. THAY ĐỔI CHÍNH SÁCH

Chúng tôi có thể cập nhật Chính sách Bảo mật này. Khi có thay đổi, chúng tôi sẽ thông báo qua ứng dụng.

## 10. LIÊN HỆ

Mọi câu hỏi về quyền riêng tư, xin gửi tại: https://github.com/iatoi/iatoi-update/issues

---

---

© 2026 IATOI. All Rights Reserved.
