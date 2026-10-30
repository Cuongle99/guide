# Phần 2: Cài đặt Theme & Cấu hình Leo Elements

Quy trình chuẩn bị thư mục theme mẫu, tối ưu hiệu suất cho môi trường phát triển và khởi tạo cấu trúc Profile trong Leo Elements.

---

## 1. Chuẩn bị và sao chép mã nguồn

* **Đổi tên thư mục theme:** Đổi tên theme mẫu (ví dụ: `theme-base-9.2` thành `leo_demo`).
* **Cập nhật `leo_demo/config.xml`:** Đổi giá trị trong thẻ `<theme_key>` thành `leo_demo` rồi lưu lại.
* **Cập nhật `leo_demo/config/theme.yml`:** Đổi `name: leo_demo` và `display_name: Demo Leo` (tên hiển thị mong muốn) rồi lưu lại.
* **Chép vào PrestaShop:**
  * Copy thư mục `leo_demo` vào thư mục `themes/` của dự án.
  * Copy toàn bộ các module trong bộ cài đè vào thư mục `modules/` của dự án.

---

## 2. Cấu hình Hiệu suất (Performance) & Kích hoạt Theme

### Tối ưu cho môi trường Dev
Truy cập **Configure > Advanced Parameters > Performance** và thiết lập:

* **Smarty:**
  * *Template compilation* = `Recompile templates if the files have been updated`
  * *Cache* = `No`
  * Nhấn **Save**.
* **Debug mode:**
  * Chuyển *Debug mode* = `Yes` -> Nhấn **Save**.
* **CCC (Combine, Compress and Cache):**
  * Chuyển cả 3 tùy chọn (*Smart cache for CSS*, *Smart cache for JavaScript*, *Apache optimization*) sang `No` -> Nhấn **Save**.

### Kích hoạt Theme
Vào **Improve > Design > Theme & Logo**, tìm đến theme vừa thêm (`Demo Leo`), chọn **Use this theme** -> **Yes**.

---

## 3. Thiết lập Hook và Profile (Leo Elements)

### Quản lý Hook
Vào **Leo Elements > Hook Manage**:
* Kéo các module mặc định không cần thiết từ cột phải sang cột *Default Modules* bên trái (tại `HOOK_NAV1`, `HOOK_NAV2`, `HOOK_TOP`, `HOOK_HOME`, `HOOK_FOOTER_BEFORE`, `HOOK_FOOTER`, `HOOK_FOOTER_AFTER`...), chỉ giữ lại **Leo Elements - Page and Content Builder**.
* Nhấn **Save Positions**.

### Tạo Profile mới
Vào **Leo Elements > Profiles: Home or LandingPage** -> Nhấn **Add new (+)**:

1. **Tab General:**
   * Nhập *Name* (ví dụ: `Home 1`) và *Friendly URL* (`home-1`).
   * Tích chọn toàn bộ các ô trong: *Fullwidth Homepage*, *Fullwidth Category Page*, *Fullwidth Product Page*, *Fullwidth Other Pages* và *Disable cache for Hooks*.
   * Nhấn **Save and Stay**.
2. **Tạo Position:**
   * Lần lượt vào các tab **Header**, **Home Content**, **Footer** -> chọn **Create a new position**, đặt tên tương ứng (`header`, `content`, `footer`) -> Nhấn **Save and Stay**.
3. **Tạo Content cho Hook:**
   * Quay lại từng tab, chọn **Create New** tại các hook cần dùng:
     * **Header:** `displayNav2`, `displayTop`.
     * **Home Content:** `displayHome`.
     * **Footer:** `displayFooter`.
   * Nhấn **Save and Stay** để hoàn tất.
