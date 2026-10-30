# Phần 1: Cài đặt PrestaShop Bản Dev

Hướng dẫn chuẩn bị mã nguồn và thiết lập môi trường PrestaShop bản Dev trên localhost (XAMPP).

---

## 1. Chuẩn bị mã nguồn

* Giải nén bộ cài bản dev (ví dụ: `prestashop_920_dev.zip`).
* Đổi tên thư mục theo tên dự án (ví dụ: `prestashop_demo`) và di chuyển vào thư mục `htdocs` của XAMPP.

---

## 2. Chạy trình cài đặt (Installation Assistant)

Truy cập đường dẫn dự án trên trình duyệt:

```text
http://localhost/<thư_mục_chứa>/prestashop_demo/
```

Thiết lập theo các thông số chuẩn sau:

| Hạng mục | Giá trị thiết lập chuẩn |
| :--- | :--- |
| **Ngôn ngữ** | `English` |
| **Điều khoản** | Tích đồng ý điều khoản sử dụng |
| **Email Admin** | `demo@demo.com` |
| **Mật khẩu Admin** | `demo6789@` |
| **Theme mặc định** | Chọn `Classic` |
| **Database** | Tạo database mới (thường đặt tiền tố `leo_...`), kiểm tra kết nối và tiến hành cài đặt |

---

## 3. Hoàn tất và Đăng nhập Quản trị (Back Office)

Sau khi cài đặt hoàn tất, mở thư mục mã nguồn dự án và đổi tên 2 thư mục quan trọng:

1. Đổi tên thư mục `install` thành `install-dev`.
2. Đổi tên thư mục `admin...` (chuỗi ngẫu nhiên do PrestaShop sinh ra) thành `admincp`.

{% hint style="success" %}
**Truy cập trang quản trị:**
Mở trình duyệt tại đường dẫn `http://localhost/<thư_mục_chứa>/prestashop_demo/admincp` và đăng nhập với tài khoản `demo@demo.com` / `demo6789@`.
{% endhint %}
