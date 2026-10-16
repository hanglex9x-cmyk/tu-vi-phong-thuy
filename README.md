# Website Tử Vi & Phong Thủy — bản GitHub Pages

Website tĩnh **1 file duy nhất** (`index.html`): mở là chạy, không cần máy chủ, không cần cài đặt.
Toàn bộ nội dung (bài viết, tử vi tuần, dịch vụ) có thể quản lý bằng **Google Sheet** —
bạn sửa Sheet là web tự cập nhật.

## 1. Cách tạo Google Sheet cho web

Tạo một Google Sheet mới với đúng **3 tab** (tên tab viết đúng như sau, có phân biệt chữ hoa/thường):

**Tab `BaiViet`** — hàng đầu tiên là tên cột:

| Ngay | ChuyenMuc | TieuDe | MoTa | NoiDung | Anh |
|------|-----------|--------|------|---------|-----|
| 10/10/2026 | Phong thủy | Tiêu đề bài… | Mô tả ngắn… | Nội dung đầy đủ… | (để trống) |

**Tab `TuViTuan`** — hàng đầu tiên là tên cột:

| Tuan | ConGiap | TongQuan | SuNghiep | TaiLoc | TinhDuyen | SucKhoe | Diem | MauMayMan | SoMayMan |
|------|---------|----------|----------|--------|-----------|---------|------|-----------|----------|
| 12/10 – 18/10/2026 | Tý | … | … | … | … | … | 7.5 | Xanh dương | 2, 9 |

**Tab `DichVu`** — hàng đầu tiên là tên cột:

| TenDichVu | MoTa | Gia |
|-----------|------|-----|
| Chấm lá số trọn đời | Luận giải chi tiết… | 500.000đ |

## 2. Chia sẻ Sheet để web đọc được

1. Trong Google Sheet, bấm **Chia sẻ** (góc phải trên).
2. Ở mục "Quyền truy cập chung", chọn **"Bất kỳ ai có đường liên kết"** → vai trò **Người xem**.
3. Bấm **Xong**. (Web chỉ đọc nội dung, không sửa được Sheet của bạn.)

## 3. Lấy Sheet ID và gắn vào web

- Mở Sheet, nhìn lên thanh địa chỉ trình duyệt, link có dạng:
  `https://docs.google.com/spreadsheets/d/`**`1AbCdEfGhIjKlMnOpQrStUvWxYz`**`/edit...`
- Phần in đậm ở giữa chính là **Sheet ID** — copy nó.
- Mở file `index.html` bằng Notepad (hoặc bất kỳ trình soạn thảo nào), tìm dòng:
  ```js
  const CONFIG = { SHEET_ID: "" }; // <-- DÁN SHEET ID VÀO ĐÂY
  ```
- Dán Sheet ID vào giữa hai dấu ngoặc kép:
  ```js
  const CONFIG = { SHEET_ID: "1AbCdEfGhIjKlMnOpQrStUvWxYz" };
  ```
- Lưu file lại. Nếu để trống (`""`), web sẽ hiển thị **dữ liệu mẫu** có sẵn.

## 4. Cập nhật nội dung

- Muốn thêm/sửa bài viết, tử vi tuần mới, dịch vụ: **sửa trực tiếp trong Google Sheet** rồi lưu.
- Mở lại web (bấm F5 tải lại trang) là nội dung mới hiện lên — không cần đụng vào code.
- Muốn thêm tuần tử vi mới: thêm 12 hàng mới trong tab `TuViTuan` với cột `Tuan` ghi tuần mới (ví dụ `19/10 – 25/10/2026`); web sẽ có ô chọn tuần.

## 5. Đăng lên GitHub Pages

1. Tạo repository mới trên GitHub (đặt tên ví dụ `tu-vi-phong-thuy`), chọn **Public**.
2. Tải file `index.html` lên repository (bấm *Add file → Upload files*).
3. Vào **Settings → Pages**, ở mục *Branch* chọn `main` (hoặc `master`), bấm **Save**.
4. Chờ 1–2 phút, web của bạn sẽ có địa chỉ dạng:
   `https://ten-tai-khoan-cua-ban.github.io/tu-vi-phong-thuy/`

## Lưu ý

- Form **đặt lịch** trong bản này chỉ hiển thị thông báo xác nhận trên trình duyệt, **chưa gửi thông tin về máy chủ** — cần bổ sung backend hoặc dịch vụ form (ví dụ Google Forms) nếu muốn nhận lịch thật.
- Form **lập lá số** tính toán hoàn toàn trên trình duyệt theo cách tính dân gian (Can Chi – Nạp Âm – Cung Phi Bát Trạch), chỉ mang tính tham khảo.
- Nội dung mẫu trong web được soạn lại bằng lời văn riêng, không sao chép nguyên văn từ trang web nào.
