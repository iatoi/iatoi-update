<div align="center">

<img src="docs/logo.png" width="96" alt="IATOI">

# IATOI Giám Sát

**Ứng dụng bảo vệ con trên mạng, điều khiển bằng Telegram.**
Cảnh báo cho bố mẹ khi con gặp nội dung nguy hiểm — bằng tiếng Việt, hiểu tiếng Việt.

[![Bản mới nhất](https://img.shields.io/github/v/release/iatoi/iatoi-update?label=b%E1%BA%A3n%20m%E1%BB%9Bi%20nh%E1%BA%A5t&color=1f7a6c)](https://github.com/iatoi/iatoi-update/releases/latest)
[![Android](https://img.shields.io/badge/Android-7.0%20tr%E1%BB%9F%20l%C3%AAn-1f7a6c)](#yêu-cầu)
[![Không cần root](https://img.shields.io/badge/kh%C3%B4ng%20c%E1%BA%A7n-root-1f7a6c)](#yêu-cầu)
[![Miễn phí](https://img.shields.io/badge/mi%E1%BB%85n%20ph%C3%AD-to%C3%A0n%20b%E1%BB%99-1f7a6c)](#giá)

### [⬇️ Tải bản mới nhất](https://github.com/iatoi/iatoi-update/releases/latest) · [📖 Hướng dẫn sử dụng](HUONG_DAN.md) · [🔒 Quyền riêng tư](CHINH_SACH_RIENG_TU.md)

</div>

---

## IATOI làm gì

Cài ứng dụng lên **máy của con**. Bố mẹ điều khiển từ **Telegram trên máy mình** — không cần cài thêm ứng dụng nào cho bố mẹ, không cần tài khoản, không cần đăng ký.

| | |
|---|---|
| 🚨 **Cảnh báo nội dung nguy hiểm** | Con gặp chuyện tự hại, ma túy, cờ bạc, dụ dỗ, lừa đảo — bố mẹ nhận tin nhắn ngay, kèm ảnh màn hình và vị trí. Bộ từ điển hơn **900 từ và cụm từ tiếng Việt**, gồm cả tiếng lóng và teencode. |
| 📍 **Biết con đang ở đâu** | Xem vị trí tức thì, theo dõi hành trình trực tiếp trên bản đồ, đặt vùng an toàn quanh nhà và trường. |
| ⏰ **Quản lý thời gian** | Giờ đi ngủ, giờ học, tổng giờ mỗi ngày, giới hạn riêng cho từng ứng dụng. |
| 📱 **Kiểm soát ứng dụng** | Khóa ứng dụng, duyệt ứng dụng mới cài, chặn con kết bạn với người lạ trên Zalo và Messenger. |
| 🛡️ **Tự bảo vệ** | Con tắt giám sát hay gỡ ứng dụng đều bị chặn lại và bố mẹ được báo ngay. |
| 📊 **Báo cáo** | Hôm nay con dùng gì, bao lâu, có gì đáng chú ý. |

Khoảng **66 lệnh** Telegram. Xem đầy đủ trong [hướng dẫn sử dụng](HUONG_DAN.md#5-danh-sách-lệnh-telegram-đầy-đủ).

---

## Ba điều nên biết trước khi dùng

**IATOI không giấu trẻ.** Ứng dụng hiện rõ trên máy con kèm thông báo *"đang được giám sát"*. Đây là lựa chọn có chủ ý: giám sát lén một đứa trẻ, đến ngày nó phát hiện, cái mất nhiều hơn cái được.

**IATOI không tự khóa máy con.** Khi phát hiện nội dung nguy hiểm, ứng dụng **chụp bằng chứng và báo cho bố mẹ** — quyết định làm gì tiếp là của bố mẹ. Máy không hiểu hoàn cảnh: một câu đùa giữa bạn bè, một đoạn lời bài hát, một bài báo con đang đọc, máy đều có thể đọc thành chuyện nghiêm trọng.

**IATOI không thay thế Google Family Link.** Family Link mạnh hơn ở phần kỷ luật (giới hạn giờ, duyệt tải ứng dụng, khóa máy) vì Google làm ra Android. IATOI mạnh ở phần Family Link không có: **hiểu nội dung tiếng Việt** con đang đọc và đang gõ. Nên cài **cả hai**, mỗi bên lo một việc — trong ứng dụng có lệnh `/familylink` hướng dẫn cách chia việc.

---

## Cài đặt

### 1. Tạo bot Telegram (làm một lần, khoảng 1 phút)

Trên máy bố mẹ, mở Telegram, nhắn cho [@BotFather](https://t.me/BotFather):

```
/newbot
```

Đặt tên cho bot, BotFather sẽ trả về một dãy **Token**. Giữ dãy này, chỉ nhập vào máy con, **không gửi cho ai**.

### 2. Cài ứng dụng lên máy con

Trên **máy của con**, mở [trang tải bản mới nhất](https://github.com/iatoi/iatoi-update/releases/latest) và tải **`app-release.apk`**.

Mở file vừa tải, Android hỏi cho phép cài từ nguồn này thì chọn **Cho phép**.

### 3. Thiết lập

Mở ứng dụng IATOI, dán Token vào ô trống, bấm **Bắt đầu kết nối**, rồi bấm **Hoàn tất thiết lập** và làm theo bảng kiểm trên màn hình.

Cuối cùng, trên máy bố mẹ nhắn cho bot một tin bất kỳ để hoàn tất ghép nối.

📖 **[Hướng dẫn đầy đủ từng bước, có bảng xử lý sự cố →](HUONG_DAN.md)**

---

## Cập nhật

Máy con **không cần cài lại tay**. Bố mẹ gõ trong Telegram:

```
/checkupdate
```

Ứng dụng cũng tự kiểm tra khoảng 24 giờ một lần. Bản mới cài đè lên bản cũ, **giữ nguyên toàn bộ cấu hình và dữ liệu**, không phải ghép nối lại.

> ⏱️ Vừa có bản mới mà `/checkupdate` còn báo bản cũ là bình thường — GitHub lưu tạm khoảng 5 phút.

---

## Tải file nào?

Mỗi bản phát hành có ba file trong mục **Assets**. Bố mẹ chỉ cần **một**:

| File | Có cần tải |
|---|---|
| **`app-release.apk`** — ứng dụng IATOI | ✅ **Tải file này** |
| `Source code (zip)` | ❌ Không |
| `Source code (tar.gz)` | ❌ Không |

Hai file `Source code` do GitHub **tự động đính kèm** vào mọi bản phát hành của mọi dự án, không ai tắt được. Chúng là ảnh chụp **của chính kho phát hành này** — tức 4 file văn bản hướng dẫn, khoảng vài KB.

> ⚠️ **Mã nguồn ứng dụng không nằm trong hai file đó** và không được phát hành công khai. Hai file này không cài lên điện thoại được; tải nhầm thì máy chỉ báo không mở được file, không hư hỏng gì.

---

## Yêu cầu

| | |
|---|---|
| **Máy con** | Android 7.0 trở lên. Từ Android 11 có thêm ảnh chụp màn hình kèm cảnh báo. |
| **Root** | Không cần. IATOI chạy trên máy chưa root. |
| **Máy bố mẹ** | Bất kỳ máy nào cài được Telegram — Android, iPhone hay máy tính. |
| **Mạng** | Máy con cần Internet. Các luật khóa và giới hạn giờ vẫn chạy khi mất mạng. |
| **Google Play Services** | Cần, để lấy vị trí GPS. |

---

## Riêng tư

IATOI **không có máy chủ**. Chúng tôi không nhận, không lưu, không nhìn thấy dữ liệu của gia đình bạn.

Dữ liệu con đi thẳng từ máy con tới **bot Telegram do chính bố mẹ tạo và sở hữu**. Token bot được mã hóa AES‑256 trong kho khóa của Android.

Ứng dụng có một tính năng tùy chọn nhờ AI đọc giúp nội dung khó hiểu; tính năng này **mặc định tắt**, bật hay không do bố mẹ quyết định bằng lệnh `/ai on|off`.

🔒 **[Đọc chính sách riêng tư đầy đủ →](CHINH_SACH_RIENG_TU.md)**

---

## Giá

**Miễn phí toàn bộ.** Không bản trả phí, không quảng cáo, không mua thêm trong ứng dụng, không giới hạn tính năng.

Đây là dự án cá nhân làm vì mục đích bảo vệ trẻ em Việt Nam. Ai thấy hữu ích và muốn góp phần duy trì thì tùy tâm.

---

## Vì sao không có trên Google Play

IATOI cần những quyền mà Google Play không cho phép ứng dụng thường dùng — cụ thể là chống trẻ tự gỡ ứng dụng và chặn trẻ tắt giám sát. Không có các quyền đó thì ứng dụng giám sát nào cũng chỉ tồn tại đến khi đứa trẻ biết cách gỡ.

Vì vậy ứng dụng được phát miễn phí ở đây, cài trực tiếp bằng file APK.

**Cài ngoài Play có an toàn không?** File APK ở đây được ký bằng chữ ký riêng của IATOI, cố định qua mọi phiên bản. Android tự kiểm chữ ký này mỗi lần cập nhật — nếu ai đó phát tán file giả mạo, máy sẽ **từ chối cài đè**. Chỉ tải từ đúng trang này.

---

## Hỏi đáp

<details>
<summary><b>Con có biết mình bị giám sát không?</b></summary>

Có, và đó là chủ ý. Ứng dụng hiện rõ trên máy kèm thông báo thường trực. IATOI có lệnh ẩn biểu tượng (`/hideicon`) cho trường hợp cần thiết, nhưng thông báo giám sát vẫn còn.
</details>

<details>
<summary><b>Trẻ gỡ được ứng dụng không?</b></summary>

Không, nếu bố mẹ đã bật **Chống gỡ** trong lúc thiết lập. Ứng dụng còn chặn trẻ trước khi kịp chạm vào các công tắc tắt giám sát trong Cài đặt, và báo cho bố mẹ mỗi lần trẻ thử.

Vẫn có một đường trẻ lớn có thể lách: khởi động máy vào **Safe Mode** — chế độ này tắt mọi dịch vụ trợ năng nên IATOI không chạy để mà chặn. Chúng tôi nói thẳng giới hạn này thay vì hứa hẹn quá tay.
</details>

<details>
<summary><b>Bố mẹ cần cài gì trên máy mình không?</b></summary>

Chỉ cần Telegram. Không có ứng dụng riêng cho bố mẹ, không tài khoản, không mật khẩu phải nhớ.
</details>

<details>
<summary><b>Một bố mẹ hay cả hai đều nhận được cảnh báo?</b></summary>

Cả hai, và nhiều hơn nữa. Người ghép nối đầu tiên là chủ nhân, sau đó thêm người bằng lệnh `/addparent`. Cũng có thể gửi cảnh báo vào một nhóm chung của gia đình.
</details>

<details>
<summary><b>Lỡ khóa quá tay, con không dùng được máy thì sao?</b></summary>

Luôn mở được từ xa qua Telegram, không cần cầm máy con. Ứng dụng IATOI được thiết kế **không thể tự khóa chính nó**, nên nó luôn sống để nghe lệnh mở khóa. Xem [mục 6 của hướng dẫn](HUONG_DAN.md#6-mở-khóa-khi-lỡ-khóa-hết-trên-máy).
</details>

<details>
<summary><b>Máy con là iPhone thì sao?</b></summary>

Không dùng được. IATOI chỉ chạy trên Android. iOS không cho phép ứng dụng đọc nội dung màn hình của ứng dụng khác.
</details>

---

## Hỗ trợ

Gặp lỗi hoặc có câu hỏi, mở một [phiếu hỗ trợ tại đây](https://github.com/iatoi/iatoi-update/issues/new/choose).

Trước khi báo lỗi, gõ `/diag` trong Telegram và chép kết quả vào phiếu — trong đó có trạng thái máy và nhật ký hoạt động gần nhất, giúp tìm nguyên nhân nhanh hơn nhiều.

> ⚠️ Khi chép nội dung `/diag`, nhớ **xóa Token bot** nếu thấy nó xuất hiện.

---

## Lịch sử phiên bản

Xem [CHANGELOG.md](CHANGELOG.md) hoặc [danh sách bản phát hành](https://github.com/iatoi/iatoi-update/releases).

---

<div align="center">

**© 2026 IATOI. All Rights Reserved.**

Phần mềm miễn phí, không dùng cho mục đích thương mại. Xem [LICENSE](LICENSE).

<sub>Kho này chứa bản cài đặt đã ký và tài liệu hướng dẫn. Mã nguồn không phát hành công khai.</sub>

</div>
