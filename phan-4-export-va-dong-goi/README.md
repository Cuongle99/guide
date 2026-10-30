# Phần 4: Export & Đóng gói Quickstart / Theme

Quy trình xuất dữ liệu mẫu, chuẩn hóa cơ sở dữ liệu, làm sạch mã nguồn và chạy script tự động đóng gói sản phẩm cuối cùng.

---

## 1. Xuất Sample Data và Data Struct từ Back Office

Vào **Leo Elements > Leo Dashboard**, cuộn xuống mục **Export Sample For Dev** (cột phải):

1. Tích chọn tất cả module (ô cạnh chữ *Name*) -> Nhấn **Create Sample** -> **OK** (hệ thống xuất tệp `.xml` vào `themes/leo_demo/samples/`).
2. Nhấn **Export Data Struct** -> **OK** (hệ thống xuất dữ liệu SQL vào `modules/leoelements/install/`).

---

## 2. Đóng gói dữ liệu mẫu vào `sample920`

### Sao chép dữ liệu
Từ thư mục dự án (`prestashop_demo`), sao chép sang thư mục công cụ `svn_leotheme\sample920`:
* Copy toàn bộ thư mục `img` vào `sample920\`.
* Copy thư mục `modules\leoelements\install` vào `sample920\` và đổi tên `install` thành `data`.

### Chuẩn hóa Charset trong `sample920\data\db_structure.sql`
Mở tệp bằng VS Code, nhấn `Ctrl + H` (Find & Replace All):
* Thay `CHARSET=utf8` thành `CHARSET=utf8mb4`.
* Thay `COLLATE=utf8_general_ci` thành `COLLATE=utf8mb4_general_ci`.
* Lưu tệp lại.

### Nén dữ liệu
* Ngoài `sample920`: Chọn 2 thư mục `data` và `img` -> Nén định dạng **ZIP** theo cú pháp `<tên_theme>_demo.zip` (ví dụ: `leo_demo_demo.zip`).

---

## 3. Dọn dẹp Theme và thêm `index.php` bảo mật

1. Copy thư mục `themes\leo_demo` từ dự án sang `svn_leotheme	hemes920\`.
2. **Dọn dẹp tệp thừa trong `themes920\leo_demo` (dùng `Shift + Delete`):**
   * Xóa thư mục `.sass-cache`.
   * Tìm kiếm và xóa toàn bộ các tệp `index.php` cũ và các tệp `.css.map`.
3. **Tự động thêm `index.php`:**
   * Mở trình duyệt truy cập `http://localhost/prestashop_install/correct_theme/`.
   * Dán đường dẫn `E:\svn_leotheme	hemes920\leo_demo` vào ô **Path to your directory**.
   * Nhấn **Add index.php** (mục *COMMON*) và đợi thông báo `DONE`.

---

## 4. Chạy Script đóng gói tự động (Git Bash)

### Cấu hình script
* Trong `svn_leotheme\sh_theme`, nhân bản một tệp `.sh` mẫu và đổi tên thành `leo_demo.sh`.
* Mở bằng VS Code, kiểm tra thông số:
  * `versions="920"`
  * `quickstart="prestashop_920.zip"`

### Thực thi trên Git Bash
Chạy lần lượt các lệnh sau:

```bash
cd /e/svn_leotheme/sh_theme
sh leo_demo.sh
```

### Kiểm tra thành phẩm
Mở thư mục `svn_leotheme\RELEASE\leo_demo` để lấy 2 bản đóng gói cuối cùng:
* `quickstart920`: Chứa bộ cài Quickstart (`leo_demo_quickstart.zip`).
* `theme920`: Chứa bộ cài riêng cho Theme (`leo_demo.zip`).
