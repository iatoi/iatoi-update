# iatoi-update

Repo public chứa **APK đã ký** + `update.json` để app IATOI Parental Control tự cập nhật qua sideload (không qua Google Play).

> ⚠️ Repo này CHỈ chứa APK ký (public cert). Keystore/private key không nằm ở đây.

## Cách dùng

Trong Telegram, phụ huynh đặt URL cập nhật:

```
/setupdateurl https://raw.githubusercontent.com/iatoi/iatoi-update/main/update.json
```

Sau đó mỗi khi có bản mới, gõ `/checkupdate` hoặc app tự quét mỗi ~24h.

## Quy trình ra bản mới (cho nhà phát triển)

1. Tăng `versionCode` / `versionName` trong `app/build.gradle.kts`.
2. Build + ký APK.
3. Tạo GitHub Release mới với tag `v<versionName>`, đính kèm `app-release.apk`.
4. Cập nhật `update.json` (đổi `versionCode`, `apkUrl`, `notes`) rồi commit.

Máy con sẽ tự nhận bản mới, không cần cài tay từng máy.