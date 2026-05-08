# BÁO CÁO BÀI TẬP: HỆ THỐNG QUẢN LÝ TIỆM CẦM ĐỒ
**Sinh viên thực hiện:** Nguyễn Thị Hằng Nga
**Lớp:** 58KTPM 
**MSSV:** K225480106050

---

##  1. THIẾT KẾ CƠ SỞ DỮ LIỆU (VIẾT TAY)
Dưới đây cs dữ liệu được viết tay dựa trên nghiệp vụ thực tế của tiệm cầm đồ (Khách hàng, Hợp đồng, Tài sản).

<img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/8ec48dec-fe65-4faf-bba6-8dca95040fc8" />

<img width="1920" height="2560" alt="image" src="https://github.com/user-attachments/assets/79e2677e-37fb-4442-9431-7d7983e7c86e" />


##  2. CẤU HÌNH DOCKER TRÊN UBUNTU
Hệ thống được đóng gói bằng Docker để đảm bảo tính đồng nhất giữa môi trường phát triển và triển khai.

### 📁 Cấu trúc dự án:
```text
quan_ly_cam_do/
├── django_app/           # Chứa mã nguồn Django
│   ├── Dockerfile        # File build image
│   └── requirements.txt  # Thư viện Python
└── docker-compose.yml    # File điều phối MariaDB, PhpMyAdmin, Django

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/668ad462-8047-432a-8faa-c8351473ee12" />

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/62e17266-9ae6-4c1e-8400-d2f3f36d815f" />

⚙️ Trạng thái các Service:
Sau khi chạy lệnh docker compose up -d, các dịch vụ đã khởi động thành công:
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/eb8aac85-a1cb-417e-8210-07bad024fdf3" />

Chạy lệnh build
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/82a9cfc2-f0ec-4cc5-a8d6-cd29bceadb1e" />

Trạng thái Service
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/58a282a9-6eab-44e9-826f-7c013fa94199" />

 3. TRIỂN KHAI DJANGO & MARIADB
 Dockerfile (Dùng sudo nano để edit)
Tôi đã cấu hình Dockerfile để cài đặt các thư viện hệ thống cần thiết cho việc kết nối Database.

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/d1922c22-5fbb-46b5-940d-fddedc08898b" />

 requirements.txt
Nội dung file bao gồm framework Django và thư viện mysqlclient để làm việc với MariaDB.

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/7d4bf975-cd0d-46d1-ad9e-fa73fff9b77a" />

*KHỞI TẠO PROJECT VÀ APP
<img width="1356" height="72" alt="image" src="https://github.com/user-attachments/assets/4daf0dbd-5fb0-48f9-9072-602931c6e2aa" />

ĐỊNH NGHĨA CƠ SỞ DỮ LIỆU (MODELS.PY)
sudo nano pawnshop/models.py
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/ef2263cc-5f31-48d4-a6d7-ee639dea170c" />

ĐĂNG KÝ VỚI TRANG ADMIN
sudo nano pawnshop/admin.py
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/fe9358c1-b79b-4eba-bd93-a0f04a09b2d3" />

Chạy lệnh cập nhật
<img width="1390" height="199" alt="image" src="https://github.com/user-attachments/assets/fc558b7b-69ee-46a3-a599-0a2e73c643f0" />

Tạo View liệt kê "Con nợ" (Views.py)
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/23035215-0669-4d9a-8ff0-8f971d1d8fed" />

Tạo giao diện
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/103a7a88-99e0-4a36-a1e5-82bafcea1b7b" />




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
