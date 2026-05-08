# BÁO CÁO BÀI TẬP: HỆ THỐNG QUẢN LÝ TIỆM CẦM ĐỒ
**Sinh viên thực hiện:** Hằng Nga
**Lớp:** 58KTPM - Khoa CNTT
**Trường:** Đại học Kỹ thuật Công nghiệp Thái Nguyên (TNUT)

---

## 📝 1. THIẾT KẾ CƠ SỞ DỮ LIỆU (VIẾT TAY)
Dưới đây là sơ đồ thực thể và các bảng dữ liệu được thiết kế tay dựa trên nghiệp vụ thực tế của tiệm cầm đồ (Khách hàng, Hợp đồng, Tài sản).

> **Ảnh chụp bản vẽ CSDL:**
> ![Sơ đồ CSDL viết tay](screenshots/csdl_viet_tay.jpg)
> *(Ghi chú: Chụp ảnh bản vẽ tay trên giấy hoặc trên bảng của bạn và đặt tên là csdl_viet_tay.jpg)*

---

## 🐳 2. CẤU HÌNH DOCKER TRÊN UBUNTU
Hệ thống được đóng gói bằng Docker để đảm bảo tính đồng nhất giữa môi trường phát triển và triển khai.

### 📁 Cấu trúc dự án:
```text
quan_ly_cam_do/
├── django_app/           # Chứa mã nguồn Django
│   ├── Dockerfile        # File build image
│   └── requirements.txt  # Thư viện Python
└── docker-compose.yml    # File điều phối MariaDB, PhpMyAdmin, Django
⚙️ Trạng thái các Service:
Sau khi chạy lệnh docker compose up -d, các dịch vụ đã khởi động thành công:

(Ghi chú: Chụp màn hình lệnh "docker ps" trong Terminal)

💻 3. TRIỂN KHAI DJANGO & MARIADB
📄 Dockerfile (Dùng sudo nano để edit)
Tôi đã cấu hình Dockerfile để cài đặt các thư viện hệ thống cần thiết cho việc kết nối Database.

(Ghi chú: Chụp ảnh bạn đang dùng sudo nano để soạn thảo Dockerfile)

📄 requirements.txt
Nội dung file bao gồm framework Django và thư viện mysqlclient để làm việc với MariaDB.

🚀 4. KẾT QUẢ THỰC HIỆN (HÌNH ẢNH CHI TIẾT)
✅ Trang Quản trị Django (Admin)
Hệ thống cho phép quản lý thêm, sửa, xóa. Các trường khóa ngoại (FK) hiển thị tên khách hàng để dễ lựa chọn.

(Ghi chú: Chụp ảnh trang Admin thêm mới hợp đồng)

✅ Kiểm chứng CSDL qua PhpMyAdmin
Tôi sử dụng PhpMyAdmin để "soi" dữ liệu thực tế lưu trong MariaDB do Django tạo ra.

(Ghi chú: Chụp màn hình danh sách các bảng trong PhpMyAdmin)

✅ Danh sách khách nợ đến hạn (Jinja2)
Trang chủ hiển thị danh sách các "con nợ" đến hạn hoặc quá hạn trả tiền dựa trên logic trong View.

(Ghi chú: Chụp màn hình trang liệt kê con nợ trên trình duyệt)

🌐 5. PUBLIC QUA CLOUDFLARE TUNNEL
Sử dụng Cloudflare Tunnel để đưa kết quả bài tập lên một sub-domain công khai.

(Ghi chú: Chụp ảnh trình duyệt hiển thị website của bạn chạy bằng link cloudflare)
