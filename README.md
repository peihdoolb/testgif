# 📦 ZSticker — Share Custom Stickers to Zalo
*(Forked from Zaticker)*

[ Tiếng Việt ](#-tiếng-việt) | [ English ](#-english)

---

## 🇻🇳 Tiếng Việt

ℹ️ **Trạng thái dự án:** Các lỗi giao diện chính đã được khắc phục. Mặc dù tần suất cập nhật có thể chậm do lịch trình cá nhân, ứng dụng vẫn hoạt động ổn định và API lấy từ Zamoji (từ năm 2018) vẫn hoạt động bình thường tính đến tháng 3/2026.

---

### 💡 Ý tưởng & Nguồn gốc

ZSticker là một dự án lập trình ngẫu hứng (vibe-coding), ra đời nhằm nghiên cứu cách Zalo xử lý việc chia sẻ sticker qua Android `Intent`.

Dự án lấy cảm hứng từ **Zamoji** — ứng dụng chính thức của VNG cho phép gửi sticker trực tiếp vào Zalo.
* **Cách phát hiện:** Dùng ADB và `logcat` để theo dõi luồng dữ liệu khi Zamoji gửi sticker sang Zalo, kết hợp dịch ngược (reverse engineering) mã nguồn Zamoji để phân tích cơ chế truyền Intent.

---

### 🎯 Mục tiêu dự án

- Cho phép người dùng thử nghiệm các bộ sticker tự tạo trên Zalo.
- Ghi lại log chi tiết (thành công / thất bại) trong quá trình truyền gửi sticker.

---

### ⚙️ Tính năng nổi bật & Trạng thái

> **Trạng thái:** Dùng tốt cho nhu cầu cơ bản (vẫn còn một số lỗi nhỏ).

* **Chia sẻ trực tiếp:** Hỗ trợ Android Share Intent (`ACTION_SEND` / `ACTION_SEND_MULTIPLE`) thẳng sang Zalo.
* **Nhập / Xuất linh hoạt:** Import ảnh đơn lẻ hoặc hàng loạt (trực tiếp trong app hoặc qua menu chia sẻ hệ thống); xuất gói sticker khi cần.
* **Tách nền ảnh (Background Removal):** Cung cấp 2 cơ chế (tùy chỉnh trong Cài đặt):
  * **Offline:** Chạy hoàn toàn trên thiết bị thông qua *Google MediaPipe Tasks Vision* (Mã nguồn mở, Apache 2.0). Dữ liệu hoàn toàn không rời khỏi thiết bị.
  * **Online:** Sử dụng mô hình *BRIA-RMBG-1.4* hosted trên HuggingFace Spaces. Endpoint proxy (`bria14proxy.vercel.app`) chỉ đóng vai trò trung gian kết nối giữa Android và HuggingFace API, hoàn toàn không lưu trữ dữ liệu hay thu thập thông tin cá nhân ([Xem mã nguồn proxy](https://github.com/huanhoahongso3-collab/BRIA-RMBG-1.4-PROXY)).
* **Giao diện:** Thiết kế theo chuẩn Google Material Design 3 (Material You).

--