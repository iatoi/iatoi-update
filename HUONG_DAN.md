# IATOI Parental Control — Hướng dẫn cài đặt & sử dụng

> **Phiên bản:** 3.8.4 (code 65) · **Nền tảng:** Android 7.0+ (minSdk 24) · **Thuần KHÔNG root**
> **Mô hình:** miễn phí dùng full, donate để duy trì dự án. Bản quyền © 2026 IATOI. All Rights Reserved.

IATOI là ứng dụng **giám sát và bảo vệ trẻ em** cài lên máy của con (máy con), điều khiển từ xa qua **Telegram Bot** trên máy của bố mẹ.
Máy con **không cần root**, không dùng Magisk — cài như app thường bằng file APK (sideload).

---

## Mục lục
1. [Trước khi bắt đầu](#1-trước-khi-bắt-đầu)
2. [Cài đặt lên máy con](#2-cài-đặt-lên-máy-con)
3. [Thiết lập lần đầu trên máy con](#3-thiết-lập-lần-đầu-trên-máy-con)
4. [Kết nối Telegram (ghép nối bố mẹ ↔ máy con)](#4-kết-nối-telegram-ghép-nối-bố-mẹ--máy-con)
5. [Danh sách lệnh Telegram đầy đủ](#5-danh-sách-lệnh-telegram-đầy-đủ)
6. [Mở khóa khi lỡ khóa hết trên máy](#6-mở-khóa-khi-lỡ-khóa-hết-trên-máy)
7. [Miễn nhiễm tự khóa — app IATOI không thể bị khóa](#7-miễn-nhiễm-tự-khóa--app-iatoi-không-thể-bị-khóa)
8. [Minh bạch & bảo mật](#8-minh-bạch--bảo-mật)
9. [Xử lý sự cố](#9-xử-lý-sự-cố)

---

## 1. Trước khi bắt đầu

**Bạn cần:**
- 1 máy con (Android 7.0 trở lên) — đây là máy của trẻ, sẽ cài IATOI.
- 1 tài khoản Telegram của bố mẹ (đã cài app Telegram trên máy bố mẹ và đăng nhập).
- 1 **Bot Token** Telegram (xem bước tạo bot bên dưới).
- File cài đặt `app-release.apk` — [tải bản mới nhất tại đây](https://github.com/iatoi/iatoi-update/releases/latest).

**Tạo Bot Telegram (1 lần duy nhất):**
1. Mở Telegram, nhắn cho [@BotFather](https://t.me/BotFather).
2. Gõ `/newbot` → đặt tên → đặt username kết thúc bằng `bot`.
3. BotFather trả về một **Token** dạng `123456789:AAH...` — **giữ bí mật**, chỉ nhập vào app trên máy con, không chia sẻ.
4. (Khuyến nghị) Gõ `/setjoingroupgroups` → chọn bot → **Disable** (để bot của AI chưa hỗ trợ group an toàn hơn; phần group bố mẹ dùng ID chat).

---

## 2. Cài đặt lên máy con

1. Trên máy con, mở [trang tải bản mới nhất](https://github.com/iatoi/iatoi-update/releases/latest) và tải **`app-release.apk`**.
   (Hoặc tải trên máy khác rồi chép sang qua USB, Google Drive, Zalo gửi tệp…)
2. Mở file APK → Android sẽ hỏi **"Cho phép cài đặt từ nguồn không xác định"** → bật cho phép.
3. Bấm **Cài đặt**. Hoàn tất → bấm **Mở**.

> Nếu máy báo "Ứng dụng không được cài đặt" vì chặn nguồn lạ: vào **Cài đặt → Ứng dụng → Truy cập đặc biệt → Cài ứng dụng không xác định** → cho phép trình duyệt/tệp đang dùng.

---

## 3. Thiết lập lần đầu trên máy con

Mở app IATOI lần đầu sẽ có **Trình hướng dẫn thiết lập** (Setup Wizard) và màn hình checklist. Làm đủ các bước để bảo vệ tối ưu:

| Bước | Mục | Vì sao cần |
|---|---|---|
| 1 | **Cho phép Trợ năng (Accessibility)** | Đây là "mắt" giám sát — quét nội dung, chặn app, đẩy về màn hình chính khi vi phạm. **Không bật = không giám sát.** |
| 2 | **Kích hoạt Device Admin** | Chống gỡ app + khóa màn hình từ xa (`/lockdevice`). |
> 💡 Nếu màn hình "chống gỡ" bị bung ra: từ v3.5.16 app đã tự mở "grace 2 phút" khi bấm HOÀN TẤT THIẾT LẬP, nên màn kích hoạt không còn bị đá ngược. Chỉ cần bấm HOÀN TẤT THIẾT LẬP rồi bấm "Kích hoạt" trên màn hình hệ thống là xong.
| 3 | **Miễn tối ưu pin (bỏ qua tối ưu pin)** | Chống hãng (OEM) giết service nền → mất kiểm soát. |
| 4 | **Nhập Bot Token** | Để IATOI kết nối và nghe lệnh từ Telegram. |
| 5 | **Đặt mã PIN** | Khóa màn hình quản lý trên máy con, trẻ không tự tắt giám sát. |
| 6 | **Bật lọc web (Private DNS)** | Làm tay 1 lần: Cài đặt → Mạng → DNS riêng tư → `dns-family.adguard.com`. |

> Sau khi thiết lập, trên máy con luôn hiển thị trạng thái **"đang được giám sát"** — minh bạch với trẻ.

---

## 4. Kết nối Telegram (ghép nối bố mẹ ↔ máy con)

1. Trên máy con, màn hình IATOI hiện một **Mã ghép nối 6 chữ số**.
2. Trên máy bố mẹ, mở Telegram → tìm bot vừa tạo → nhắn **đúng mã 6 chữ số đó**.
3. Bot phản hồi **đã ghép nối** → bố mẹ trở thành **CHỦ NHÂN** (người điều khiển).
4. Muốn thêm bố/mẹ phụ: chủ nhân gõ `/addparent <chat_id>` → người kia nhắn `/join <mã>` để xác nhận.

> Lấy `chat_id` bằng cách bảo phụ huynh kia nhắn bot 1 lần trước.
> Các lệnh nhạy cảm (`/setpin`, `/addparent`, `/delparent`, `/setchannel`, `/reboot`, `/setupdateurl`) **chỉ chủ nhân** dùng được.

---

## 5. Danh sách lệnh Telegram đầy đủ

### 🔐 Ghép nối & quản trị
| Lệnh | Tác dụng |
|---|---|
| `<mã 6 số>` | Ghép nối trở thành chủ nhân |
| `/addparent <id>` | Mời thêm phụ huynh phụ |
| `/join <mã>` | Phụ huynh phụ xác nhận lời mời |
| `/listparents` | Xem phụ huynh + kênh báo cáo |
| `/delparent <id>` | Xóa phụ huynh phụ |
| `/setgroup` | Chốt group bố mẹ (gõ NGAY TRONG group) |
| `/setchannel group\|private` | Kênh báo cáo: group hay 1:1 |
| `/setpin <4-6 số>` | Đặt/lại mã PIN (khi quên PIN) |
| `/say <lời>` | Nhắn hiện lên màn hình máy con |

### 📱 Kiểm soát app
| Lệnh | Tác dụng |
|---|---|
| `/apps` | Liệt kê app trên máy con |
| `/lock <tên app>` | Khóa app (vd `/lock YouTube`) |
| `/unlock <tên app>` | Mở khóa hoàn toàn |
| `/approve <tên app>` | Duyệt app vừa cài (mở khóa) |
| `/disallow <tên app>` | Bỏ duyệt + giữ chặn |
| `/listblocked` | Xem app đang bị khóa |
| `/strictmode on\|off` | Chỉ cho chạy app đã duyệt (mạnh nhất) |
| `/allow <tên>` · `/listallowed` | Cho phép / xem app đã duyệt |
| `/locksettings` · `/unlocksettings` | Khóa/mở ứng dụng Cài đặt |
| `/opensettings [phút]` | Mở cửa Cài đặt **tạm thời cho bố mẹ** (mặc định 10 phút, tối đa 60, tự đóng). `/opensettings off` đóng ngay |
| `/categories` | Xem danh mục app (Game/MXH/Video…) |
| `/categorylimit <MÃ> <phút>` | Giới hạn theo danh mục (vd `/categorylimit GAME 60`) |

### ⏰ Kiểm soát thời gian
| Lệnh | Tác dụng |
|---|---|
| `/lockdevice` · `/unlockdevice` | Khóa/mở toàn máy ngay |
| `/bedtime 22:00 06:00` | Giới nghiêm ngày thường |
| `/bedtime weekend 23:00 07:00` | Giới nghiêm cuối tuần |
| `/bedtime off` | Tắt giới nghiêm |
| `/schooltime 08:00 16:00` | Khóa máy giờ học ban ngày |
| `/daylimit 180` · `/daylimit off` | Tổng giờ dùng máy/ngày |
| `/daybonus 15` | Cấp thêm 15 phút tổng hôm nay |
| `/longsession 120` | Báo khi dùng liên tục 120 phút không nghỉ |
| `/applimit <tên> 60` · `off` | Giới hạn phút/ngày cho 1 app |
| `/appwindow <tên> 18:00 20:00` | Chỉ cho mở app trong khung giờ |
| `/listlimits` · `/listwindows` · `/apprules` | Xem giới hạn/khung giờ/tổng quan |

### 🌐 Lọc nội dung
| Lệnh | Tác dụng |
|---|---|
| `/safeweb on\|off` | Bật/tắt lọc web (hướng dẫn Private DNS) |
| `/blockurl <tên miền>` | Chặn web cụ thể |
| `/listurls` | Xem danh sách web chặn |
| `/keywords add\|del <từ>` | Quản lý từ khóa nhạy cảm |

### 📍 Vị trí & theo dõi
| Lệnh | Tác dụng |
|---|---|
| `/location` | Vị trí con ngay (kèm link Google Maps) |
| `/trackgps 30` · `off` | Tự gửi GPS mỗi 30 phút |
| `/livegps 30` · `off` | Chia sẻ hành trình TRỰC TIẾP (chấm tự chạy trên bản đồ) |
| `/autolive on\|off` | Tự chia sẻ hành trình 2 khung/ngày |
| `/autolive 07:15 08:15 16:15 19:15` | Đổi khung giờ tự chia sẻ |
| `/locationhistory [n]` | Lịch sử vị trí |
| `/setzonehere <tên> [bán kính m]` | Đặt vùng an toàn (Nhà/Trường) tại chỗ con |
| `/setzone <tên> <lat> <lng>` · `/listzones` · `/delzone` | Quản lý vùng an toàn |

### 📊 Báo cáo & chẩn đoán
| Lệnh | Tác dụng |
|---|---|
| `/report` · `/weekreport` | Báo cáo dùng app hôm nay / 7 ngày |
| `/alerts` | Lịch sử báo động (lọc `red\|orange\|info\|keyword\|install…`) |
| `/status` | Trạng thái máy con |
| `/checkup` | Kiểm tra thiết lập đã đủ chưa |
| `/ping` | Máy con còn online không |
| `/diag [n]` | Chẩn đoán + log hoạt động gần nhất |
| `/today` | **Hôm nay con thế nào** — tóm tắt một tin nhắn, kèm việc bố mẹ nên làm |
| `/guard` | Lá chắn còn nguyên không: 5 lớp phòng thủ, lớp nào đang hở, cách vá |
| `/help` | 6 việc hay dùng nhất (`/help all` xem đầy đủ) |

### 🛡️ Lá chắn & tiện ích
| Lệnh | Tác dụng |
|---|---|
| `/guard` | Xem đủ 5 lớp tự vệ và lớp nào đang hở |
| `/opensettings [phút]` | Mở cửa Cài đặt tạm thời cho bố mẹ (mặc định 10 phút, tối đa 60). `off` đóng ngay |
| `/ai on\|off` | Cho phép hay không cho AI đọc nội dung màn hình (**mặc định tắt**) |
| `/familylink` | Hướng dẫn dùng IATOI cùng Google Family Link |
| `/deviceowner` | Đặt IATOI làm chủ sở hữu thiết bị — mức bảo vệ cao nhất |
| `/hideicon` · `/showicon` | Ẩn / hiện biểu tượng IATOI trên màn hình máy con |
| `/checkupdate` | Kiểm tra và cài bản mới |
| `/lockdevice` · `/unlockdevice` | Khóa / mở toàn máy ngay lập tức |

---

## 6. Mở khóa khi lỡ khóa hết trên máy

> Đây là "phao cứu sinh". Nếu lỡ khóa quá tay (khóa nhiều app, khóa cả Cài đặt, khóa cả máy), **luôn còn đường mở qua Telegram**.

**Vì sao an toàn:** App IATOI được thiết kế **miễn nhiễm** — không thể bị khóa, không thể giới hạn, không thể nhốt trong khung giờ (xem mục 7). Nên nó **luôn sống** để nghe lệnh mở khóa từ bạn.

| Tình huống | Lệnh mở khóa |
|---|---|
| Khóa 1 app lỡ tay | `/unlock <tên app>` |
| Khóa cả Cài đặt (Settings) | `/unlocksettings` |
| Bị đá ra khi mở Trợ năng / Tự khởi động / Chống gỡ / Khôi phục gốc | `/opensettings 10` |
| Khóa toàn máy (`/lockdevice`) | `/unlockdevice` |
| Chế độ nghiêm ngặt chặn quá nhiều app | `/strictmode off` |
| Giới hạn giờ quá chặt | `/applimit <tên> off` · `/daylimit off` |
| Giới nghiêm / giờ học đang khóa | `/bedtime off` · `/schooltime off` |

**Thứ tự khuyến nghị khi "khóa hết":**
1. `/unlockdevice` — mở máy.
2. `/strictmode off` — tắt chế độ chỉ chạy app duyệt.
3. `/unlocksettings` — mở lại Cài đặt.
4. `/unlock <tên app>` cho từng app cần — hoặc `/apprules` để xem đang khóa gì rồi gỡ.

> Chỉ cần **điện thoại bố mẹ có Telegram + mạng** là mở được, **không cần cầm máy con**, không cần root, không cần reset.

---

## 7. Miễn nhiễm tự khóa — app IATOI không thể bị khóa

Từ **v3.5.15**, app IATOI có cơ chế **chống tự-sát** bảo vệ chính nó:

- `PolicyManager` (chốt chặn khóa app): **từ chối** đưa `com.iatoi.parentalcontrol` vào danh sách chặn; `isAppBlocked` luôn trả `false` cho chính nó.
- `AppLimitManager` (chốt giới hạn giờ/khung giờ): **bỏ qua** mọi `setLimit`/`setWindow` nhắm vào chính nó.
- Lệnh `/lock com.iatoi.parentalcontrol` → bot trả về cảnh báo "không thể khóa chính IATOI".
- Lệnh `/categorylimit OTHER` (danh mục chưa phân loại) → tự loại IATOI ra khỏi danh sách.

**Kết quả:** dù gõ nhầm lệnh, dù trẻ cố khóa, dù logic nào chạy — **IATOI luôn hoạt động** để bố mẹ còn đường điều khiển. Chốt chặn đặt ở **tầng dữ liệu** (1 điểm duy nhất) nên phủ hết mọi ngả vào (Telegram, app UI, quy tắc tự động).

---

## 8. Minh bạch & bảo mật

- **Minh bạch:** app hiển thị rõ trên máy con + thông báo "đang được giám sát". Không giấu giếm, phù hợp đạo đức giám sát trẻ em và Play Protect.
- **Thuần không root:** không dùng quyền root, không phá vỡ hệ thống.
- **Dữ liệu nằm tại máy:** luật khóa/giới hạn/từ khóa được lưu trên máy con, **vẫn hoạt động khi mất mạng**.
- **Bot Token & PIN:** giữ bí mật, chỉ nhập vào máy con. Không gửi token qua chat, không lưu vào file.
- **Phân quyền:** chỉ **chủ nhân** dùng được lệnh nhạy cảm; phụ huynh phụ phải được mời qua mã xác nhận 2 chiều.
- **Gọi mạng:** Telegram bot (polling) và Google Play Services Location. Có timeout + tự phục hồi khi mất mạng.
- **AI đám mây (tùy chọn, MẶC ĐỊNH TẮT):** IATOI có thể nhờ AI đọc giúp những đoạn khó hiểu. Khi TẮT — trạng thái mặc định — **không một chữ nào trên màn hình con rời khỏi máy**. Bật/tắt bằng `/ai on|off`, xem trạng thái bằng `/diag`. Chi tiết trong [chính sách riêng tư](CHINH_SACH_RIENG_TU.md).

---

## 9. Xử lý sự cố

| Triệu chứng | Cách xử lý |
|---|---|
| Bot không phản hồi lệnh | Kiểm tra máy con có mạng + app IATOI còn chạy. Gõ `/ping` thử. |
| Không giám sát (không chặn app) | **Chưa bật Trợ năng.** Mở app IATOI → "HOÀN TẤT THIẾT LẬP" → bật Trợ năng. |
| Máy con hay mất kiểm soát | Chưa **miễn tối ưu pin** → bật bỏ qua tối ưu pin. Gõ `/checkup` để xem thiếu gì. |
| Xuất hiện cảnh báo trẻ tắt Trợ năng | Máy không root → không tự bật lại được; cầm máy con bật lại Trợ năng. |
| Không lấy được vị trí | Bật GPS + quyền vị trí "Luôn cho phép" trên máy con. |
| Quên PIN mở app | Chủ nhân gõ `/setpin <mã mới>` để đặt lại PIN từ xa. |
| Cài bản mới lên bản cũ | APK cùng chữ ký → cài đè giữ nguyên dữ liệu (không cần gỡ). |
| Chẩn đoán sâu | Gõ `/diag 25` — bot trả về log hoạt động + trạng thái đầy đủ để phân tích. |

---

> **Mẹo nhanh:** Sau khi cài xong luôn chạy `/checkup` và `/status` để xác nhận bảo vệ đang hoạt động đầy đủ, rồi đặt `/bedtime` + `/strictmode on` nếu muốn bảo vệ mạnh nhất.