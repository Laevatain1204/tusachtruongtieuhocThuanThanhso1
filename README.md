# 📚 Thư Viện Đại Sứ Văn Hóa Đọc

Website thư viện số dành cho cộng đồng yêu đọc sách, xây dựng bằng HTML/CSS/JavaScript thuần — có thể triển khai trực tiếp trên **GitHub Pages**.

---

## 🗂 Cấu Trúc File

```
library-website/
├── index.html     → Trang chủ (công khai — tra cứu tài liệu)
├── admin.html     → Trang quản trị (chỉ admin)
├── viewer.html    → Trang xem tài liệu (PDF & DOCX)
└── README.md
```

---

## 🚀 Triển Khai Lên GitHub Pages

### Bước 1 — Tạo Repository
1. Vào [github.com](https://github.com) và tạo repository mới
2. Đặt tên (VD: `thu-vien-van-hoa-doc`)
3. Chọn **Public**

### Bước 2 — Upload File
Kéo 3 file `index.html`, `admin.html`, `viewer.html` vào repository.

### Bước 3 — Bật GitHub Pages
1. Vào **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / **root**
4. Nhấn **Save**

### Bước 4 — Truy Cập
Sau vài phút, website sẽ chạy tại:
```
https://<username>.github.io/<repo-name>/
```

---

## 🔐 Thông Tin Đăng Nhập Admin

| Thông tin | Giá trị |
|-----------|---------|
| Tên đăng nhập | `admin` |
| Mật khẩu | `daisu2024` |

> ⚠️ **Lưu ý bảo mật:** Đây là thông tin đăng nhập mặc định được mã hóa cứng trong file `admin.html`. Để bảo mật hơn, bạn có thể đổi mật khẩu bằng cách chỉnh dòng `ADMIN_PASS` trong file `admin.html`.

---

## ✨ Chức Năng

### 🌐 Trang Công Khai (`index.html`)
- Trang chủ với hero banner đẹp mắt
- Thanh tìm kiếm tài liệu theo tiêu đề, tác giả, danh mục
- Lọc theo danh mục: Văn học, Lịch sử, Khoa học, Giáo dục, Nghệ thuật
- Hiển thị tài liệu nổi bật (2 tài liệu mới nhất)
- Grid tài liệu với card đẹp
- Thống kê số tài liệu và danh mục

### 🔒 Trang Admin (`admin.html`)
- Màn hình đăng nhập bảo mật
- **Tab Đăng Tải:** Upload tài liệu PDF/DOCX với kéo-thả
  - Nhập tiêu đề, tác giả, danh mục, năm, mô tả
  - Thanh tiến trình khi upload
- **Tab Quản Lý:** Xem và xóa tài liệu đã đăng
- Dashboard thống kê tổng quan

### 📖 Trang Xem Tài Liệu (`viewer.html`)
- **PDF:** Hiển thị trực tiếp trong iframe
- **DOCX:** Chuyển đổi và hiển thị HTML với thư viện mammoth.js
- Sidebar thông tin tài liệu chi tiết
- Nút tải xuống tệp gốc

---

## 💾 Lưu Trữ Dữ Liệu

Website sử dụng **localStorage** của trình duyệt để lưu tài liệu:
- Không cần backend hay server
- Dữ liệu lưu trực tiếp trên máy của admin khi upload
- **Lưu ý:** Tài liệu chỉ hiển thị trên cùng thiết bị/trình duyệt đã upload

> 💡 **Để chia sẻ tài liệu cho nhiều người:** Mỗi lần admin đăng nhập và upload từ thiết bị của mình, dữ liệu sẽ lưu trong localStorage của trình duyệt đó. Người dùng truy cập từ máy khác sẽ không thấy tài liệu trừ khi cùng thiết bị.
>
> **Giải pháp nâng cao:** Tích hợp Firebase Firestore + Firebase Storage để lưu tài liệu trên cloud (cần thêm cấu hình).

---

## 🎨 Thiết Kế

- Phong cách **thư viện cổ điển sang trọng** với tông màu Burgundy + Vàng
- Font chữ: Playfair Display + Cormorant Garamond + EB Garamond
- Responsive cho cả mobile và desktop
- Animation mượt mà
- Hỗ trợ tiếng Việt đầy đủ

---

## 📝 Tuỳ Chỉnh

### Đổi mật khẩu admin
Mở `admin.html`, tìm và sửa:
```javascript
const ADMIN_PASS = 'daisu2024'; // Đổi thành mật khẩu của bạn
```

### Thêm danh mục
Mở `index.html` và `admin.html`, tìm phần `filter-btn` / `<select>` và thêm danh mục mới.

### Đổi màu sắc
Sửa CSS variables `:root` trong mỗi file HTML.

---

*Được xây dựng với ❤️ cho cộng đồng Văn Hóa Đọc Việt Nam*
