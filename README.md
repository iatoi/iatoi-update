# IATOI — Bản cài đặt và cập nhật

Đây là nơi tải **ứng dụng IATOI Parental Control** cho điện thoại Android của con.

👉 **[Tải bản mới nhất tại đây](https://github.com/iatoi/iatoi-update/releases/latest)**

---

## Tải file nào?

Ở mỗi phiên bản, phần **Assets** có ba file. Bố mẹ **chỉ cần một file duy nhất**:

| File | Là gì | Có cần tải không |
|---|---|---|
| **`app-release.apk`** | Ứng dụng IATOI, cài lên máy con | ✅ **Tải file này** |
| `Source code (zip)` | GitHub tự đính kèm, xem giải thích bên dưới | ❌ Không |
| `Source code (tar.gz)` | Cùng nội dung, chỉ khác định dạng nén | ❌ Không |

Hai file `Source code` do GitHub **tự động tạo** cho mọi phiên bản của mọi dự án, không ai tắt được. Chúng là ảnh chụp **của chính kho này** — tức chỉ gồm 3 file cấu hình (`README.md`, `update.json`, `.gitignore`), tổng cộng khoảng **1,5 KB**.

> ⚠️ Nói cho rõ: **mã nguồn ứng dụng IATOI không nằm trong hai file đó** và không được phát hành công khai. Kho chứa mã nguồn là kho riêng tư. Hai file này không cài lên điện thoại được; tải nhầm thì máy chỉ báo không mở được file, không hư hỏng gì.

---

## Cách cài lần đầu

1. Trên **máy của con**, mở link phiên bản mới nhất ở trên, tải `app-release.apk`.
2. Mở file vừa tải. Android sẽ hỏi cho phép cài ứng dụng từ nguồn này — chọn **Cho phép**.
3. Mở app IATOI, làm theo bảng kiểm hiện trên màn hình.

📖 Hướng dẫn đầy đủ, có ảnh và giải thích từng bước: **[HUONG_DAN.md](https://github.com/iatoi/iatoi-parental-control/blob/main/HUONG_DAN.md)**

---

## Cách cập nhật khi có bản mới

Máy con **không cần cài lại tay**. Trong Telegram, bố mẹ gõ:

```
/checkupdate
```

App cũng tự kiểm tra khoảng 24 giờ một lần và báo lên máy con khi có bản mới.

Bản mới cài đè lên bản cũ, **không mất cấu hình, không mất dữ liệu**, không phải ghép nối lại Telegram.

Nếu đây là lần đầu dùng tính năng cập nhật, gõ một lần lệnh sau để chỉ cho app biết chỗ tìm bản mới:

```
/setupdateurl https://raw.githubusercontent.com/iatoi/iatoi-update/main/update.json
```

> ⏱️ Vừa có bản mới mà `/checkupdate` còn báo bản cũ là **bình thường** — GitHub lưu tạm khoảng 5 phút. Chờ một lát rồi gõ lại.

---

## Câu hỏi thường gặp

**Vì sao không tải trên Google Play?**
IATOI dùng những quyền mà Google Play không cho phép với ứng dụng thường (như chặn con gỡ ứng dụng). App được phát miễn phí ngoài Play, cài trực tiếp bằng file APK.

**Cài ngoài Play có an toàn không?**
File APK ở đây được ký bằng chữ ký riêng của IATOI, cố định qua mọi phiên bản. Android tự kiểm chữ ký này mỗi lần cập nhật — nếu ai đó đưa file giả, máy sẽ **từ chối cài đè**.

**Máy con cần Android mấy?**
Android 7.0 trở lên. Máy Android 11 trở lên có thêm tính năng chụp ảnh màn hình làm bằng chứng khi báo động.

**Có cần root máy không?**
Không. IATOI chạy hoàn toàn trên máy chưa root.

---

## Dành cho người phát triển

Kho công khai này chỉ chứa APK đã ký (kèm chứng chỉ công khai) và file `update.json`.
**Khóa ký (keystore), mật khẩu và mã nguồn không nằm ở đây** — mã nguồn để trong kho riêng tư.

Quy trình ra bản mới:

1. Tăng `versionCode` / `versionName` trong `app/build.gradle.kts`.
2. Build và ký APK bằng `tools/sign_release.sh`.
3. Tạo Release với tag `v<versionName>`, đính kèm `app-release.apk`.
4. Cập nhật `update.json` (`versionCode`, `versionName`, `apkUrl`, `notes`).

⚠️ Phải làm **release trước, `update.json` sau**. Làm ngược lại sẽ có một khoảng thời gian `update.json` trỏ tới file chưa tồn tại, máy con tải về lỗi 404.

---

© 2026 IATOI. All Rights Reserved. Phần mềm miễn phí, không thương mại.
