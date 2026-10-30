# Phần 3: Cấu hình Font chữ & Biến màu sắc (SCSS)

Hướng dẫn chạy trình biên dịch SCSS (Compass), nhúng Google Fonts và thiết lập hệ thống biến màu sắc từ bản thiết kế Figma.

---

## 1. Khởi chạy trình biên dịch Compass

* Mở thư mục theme (`themes/leo_demo`) bằng **VS Code**.
* Mở Terminal (**Terminal > New Terminal**), chạy lệnh sau để tự động biên dịch `.scss` sang `.css`:

```bash
compass watch
```

---

## 2. Khai báo và nhúng Google Fonts

### Bước 1: Lấy mã `@font-face`
* Kiểm tra tên font trên Figma (mục *Typography*, ví dụ: `Inter Tight`).
* Truy cập **Google Fonts**, chọn font -> **Get font** -> **Get embed code**.
* Copy URL trong thuộc tính `href` của thẻ `<link>`, mở trên tab trình duyệt mới và copy toàn bộ mã `@font-face`.

### Bước 2: Nhúng vào dự án
* Mở tệp `_dev/css/partials/_fonts.scss`.
* Dán mã `@font-face` vào dưới phần khai báo font icon mặc định (trước dòng `/* stylelint-enable */`) và lưu lại.

### Bước 3: Cập nhật biến Font
* Mở tệp `_dev/css/_base_variables.scss`.
* Thay giá trị của các biến sau thành `"Inter Tight", sans-serif;`:

```scss
--font-family-base: "Inter Tight", sans-serif;
--font-family-megamenu: "Inter Tight", sans-serif;
--font-family-slider: "Inter Tight", sans-serif;
--font-family-heading: "Inter Tight", sans-serif;
--font-family-senary: "Inter Tight", sans-serif;
```

---

## 3. Cấu hình biến màu sắc (Color Variables)

Trong tệp `_dev/css/_base_variables.scss`, đối chiếu mã màu từ Figma và cập nhật:

### Màu chủ đạo (`//color skin`)
* `--theme-color-default`: Màu chủ đạo của thiết kế (ví dụ: `#DBAF2B`).

### Màu văn bản & liên kết (`// Color Text`)
* `--head-t-color`: Màu tiêu đề Heading (ví dụ: `#121212`).
* `--link-color`: Màu đường dẫn liên kết (ví dụ: `#121212`).
* `--text-color`: Màu văn bản nội dung Body (ví dụ: `#545454`).
* `--price-color`: Màu giá sản phẩm (ví dụ: `#121212`).

### Màu nút bấm (`//Button`)
* `--btn-bg`: Màu nền mặc định (ví dụ: `#121212`).
* `--btn-bg-hover`: Màu nền khi di chuột (thường giữ nguyên `var(--theme-color-default);`).
* `--btn-color` & `--btn-color-hover`: Màu chữ mặc định và khi hover (ví dụ: `#FFFFFF`).

{% hint style="info" %}
Lưu tệp (`Ctrl + S`) và kiểm tra cửa sổ Terminal báo `write assets/css/theme.css` để đảm bảo CSS đã được cập nhật.
{% endhint %}
