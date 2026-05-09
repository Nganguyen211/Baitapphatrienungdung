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


## Cấu trúc dự án

quan_ly_cam_do/
├── django_app/           # Chứa mã nguồn Django
│   ├── Dockerfile        # File build image
│   └── requirements.txt  # Thư viện Python
└── docker-compose.yml    # File điều phối MariaDB, PhpMyAdmin, Django

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/3e5a7015-417f-4504-80b7-1b1dcaf20bd9" />


<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/62e17266-9ae6-4c1e-8400-d2f3f36d815f" />


⚙️ Trạng thái các Service:

Sau khi chạy lệnh docker compose up -d, các dịch vụ đã khởi động thành công:

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/eb8aac85-a1cb-417e-8210-07bad024fdf3" />


Chạy lệnh build

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/82a9cfc2-f0ec-4cc5-a8d6-cd29bceadb1e" />

Trạng thái Service

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/58a282a9-6eab-44e9-826f-7c013fa94199" />

 ## 3. TRIỂN KHAI DJANGO & MARIADB
    
Dockerfile (Dùng sudo nano để edit)

Tôi đã cấu hình Dockerfile để cài đặt các thư viện hệ thống cần thiết cho việc kết nối Database.

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/d1922c22-5fbb-46b5-940d-fddedc08898b" />

Requirements.txt
 
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

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/5ddf4027-0377-490f-a990-cee39d4c80bc" />

Tạo View liệt kê "Con nợ" (Views.py)

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/23035215-0669-4d9a-8ff0-8f971d1d8fed" />

Tạo giao diện

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/103a7a88-99e0-4a36-a1e5-82bafcea1b7b" />

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/40a91dcd-9da0-42ce-a49e-702f27261e43" />



## 4. KẾT QUẢ THỰC HIỆN (HÌNH ẢNH CHI TIẾT)
Trang Quản trị Django (Admin)

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/38583b59-f8ca-4c01-8453-ec54c4e318e2" />

Hệ thống cho phép quản lý thêm, sửa, xóa. Các trường khóa ngoại (FK) hiển thị tên khách hàng để dễ lựa chọn.

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/5120dcba-e2e6-4e36-8cbe-4a6b844fc88f" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/059c2053-7ec3-4e7f-8c70-b7af05166627" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/d50a8ccd-b7fb-4e0b-8040-65415ad1b958" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/b32059b9-0334-421f-a2a8-5c9576983663" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/f83d29c1-d1a8-4502-8856-4f6d632d2d00" />

<img width="1920" height="1020" alt="Screenshot 2026-05-09 200626" src="https://github.com/user-attachments/assets/2ecc8a20-f361-41ae-988c-e8c93508c97c" />

✅ Kiểm chứng CSDL qua PhpMyAdmin

Tôi sử dụng PhpMyAdmin để "soi" dữ liệu thực tế lưu trong MariaDB do Django tạo ra.

sudo nano django_app/core/settings.py và thay thế đoạn DATABASES cũ bằng đoạn này:

Python

DATABASES = {

    'default': {
    
        'ENGINE': 'django.db.backends.mysql',
        
        'NAME': 'db_cam_do',        # Khớp với MARIADB_DATABASE

        'USER': 'user_nga',         # Khớp với MARIADB_USER
        
        'PASSWORD': 'password_nga', # Khớp với MARIADB_PASSWORD
        
        'HOST': 'db',               # Tên service MariaDB của Nga
        
        'PORT': '3306',
        
    }
    
}

Sau đó Nga chạy các lệnh này để hoàn tất:

Cài đặt thư viện kết nối (nếu chưa có):

sudo docker-compose exec web pip install mysqlclient

Đẩy bảng sang MariaDB:

sudo docker-compose exec web python manage.py migrate

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/5d7454fc-5cae-40f1-a280-d2e1308b104b" />

✅ Danh sách khách nợ đến hạn (Jinja2)

Cấu hình URL

Mở django_app/core/urls.py và thêm đường dẫn:

from pawnshop.views import home_page

urlpatterns = [

    path('admin/', admin.site.urls),
    
    path('', home_page, name='home'), # Trang chủ
    
]

Trang chủ hiển thị danh sách các "con nợ" đến hạn hoặc quá hạn trả tiền dựa trên logic trong View.

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/91e1d082-ce7a-4fe9-a983-eb738c8033a2" />

# 5. PUBLIC QUA CLOUDFLARE TUNNEL

Sử dụng Cloudflare Tunnel để đưa kết quả bài tập lên một sub-domain công khai.

Tải và cài đặt Cloudflared

Bash

wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb

Chạy lệnh lấy link Public

Bash

cloudflared tunnel --url http://localhost:8000

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/3f60f846-f3b6-46ea-8241-9f7c59b0c0ca" />

Link công khai :https://covered-grew-pete-galleries.trycloudflare.com

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8a1daac8-445a-4404-ba29-57d180fecce2" />

