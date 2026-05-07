# BÁO CÁO BÀI TẬP LỚN - HỆ THỐNG WEB & DOCKER
**Sinh viên:** Nguyễn Thị Hằng Nga


# PHẦN A: ĐĂNG KÝ TÊN MIỀN & CLOUDFLARE

### 1. Đăng ký tên miền tại Mắt Bão
- Tên miền đã chọn: `yourdomain.id.vn`
- Trạng thái: Đã xác thực eKYC.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c749e343-0565-417d-a87f-83cbe3a24119" />


### 2. Cấu hình DNS Cloudflare
- Đã trỏ Nameservers từ Mắt Bão sang Cloudflare.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/537da718-908e-4dd0-b438-2da7e4dd712c" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d4542f7f-c662-4cc3-95e0-cf044eebefec" />


# PHẦN B: CÀI ĐẶT UBUNTU & DOCKER

### 1. Thông tin hệ thống
- Hệ điều hành: Ubuntu 24.04 LTS 
- IP máy chủ: `192.168.x.x`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5ecbccab-c221-4ff9-88e3-fdd7f793ac29" />


### 2. Cài đặt Docker & SSH
- Đã cài đặt Docker và Docker-compose plugin.
- Đã cấu hình Group Docker để chạy không cần `sudo`.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5f1518bf-f23f-4e98-a962-395426fbc45a" />


### 3. Cấu hình tường lửa UFW
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5755670d-8991-4788-a20a-4de3afc2c88e" />


# PHẦN C: CẤU HÌNH DOCKER COMPOSE

### 1. Cấu trúc thư mục trên ổ D
- Đường dẫn: 'D/myapp`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c97e4cd6-4afa-423b-a140-69555b430f45" />


### 2. File cấu hình Nginx & Docker-compose
hangnga@DESKTOP-P15R9MR:/mnt/d/myapp/nginx$ nano nginx.conf
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9907bffc-abe1-43d0-974a-9fbbc90826ad" />

hangnga@DESKTOP-P15R9MR:/mnt/d/myapp$ nano docker-compose.yml
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0f7d4da1-1ef1-41cd-9d21-50fe4615a3ec" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/65821818-131c-4264-a675-14adf4ad67b5" />


# PHẦN D: BONUS - ỨNG DỤNG FLASK API

### 1. Mã nguồn API
- Ngôn ngữ: Python 3.9 Slim.
- Framework: Flask.
Tạo file code Python (app.py):
hangnga@DESKTOP-P15R9MR:/mnt/d/myapp$ nano myapi/app.py
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6320541a-6b59-4421-8999-c3bcc73c414d" />

Tạo file danh sách thư viện (requirements.txt):
Tạo file đóng gói (Dockerfile):
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/23a795ab-2022-47bd-8ddc-eb47eb3410e2" />
Mã nguồn API
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3d903fce-e660-4a33-ac85-73290e8effdf" />


### 2. Xây dựng Image
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d02db98d-70df-46f1-9169-766b76ae0758" />


# PHẦN E: TRIỂN KHAI & KIỂM THỬ

### 1. Khởi chạy hệ thống
- Lệnh: `docker compose up -d`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ffe464c8-7fe1-412e-9c54-29860e519c54" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6130f5e0-ce8d-4b69-8f1c-97af5e37f960" />

### 2. Kiểm tra các dịch vụ
- Truy cập Web cá nhân qua Localhost.
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0cb6d2c7-c7a0-41be-a449-b242c514666a" />

- Truy cập Node-RED qua cổng 1880.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/53478190-2c5a-4543-94a4-de78f1bd889d" />


# PHẦN F: GỠ LỖI & QUẢN LÝ TÀI NGUYÊN

### 1. Kiểm tra Logs
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8e2a2aa0-125b-40ad-b04e-97d23803dcdd" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3e561ca6-de7c-43ba-8300-ad89e9c2ecb3" />


### 2. Giới hạn tài nguyên (Resources)
- Đã giới hạn RAM 512M cho service.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/60d41144-63b8-4c13-a7af-a6601a3f35c8" />

# PHẦN G: TRIỂN KHAI END-USER & TRẢ LỜI CÂU HỎI

### 1. Cloudflare Tunnel
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e05474ec-e548-4f7f-98ba-c6c158249943" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/dc022ede-60cb-4961-bafd-b2b42f69dccf" />

- Trạng thái Tunnel: Healthy.
  <img width="1553" height="883" alt="image" src="https://github.com/user-attachments/assets/92b580c2-4cbc-4154-9411-b537de9bdc84" />

- Public Hostname: `https://hangnga23.io.vn`


### 2. Trả lời câu hỏi lý thuyết
1 Tại sao dùng Nginx làm Reverse Proxy? Trả lời: Để quản lý tập trung các dịch vụ trên cùng một cổng 80, tăng tính bảo mật và dễ dàng cấu hình SSL/TLS sau này.

2 Sự khác biệt Mount file và Mount thư mục? Trả lời: Mount file gắn kết 1 file duy nhất (như config), mount thư mục gắn kết toàn bộ folder dữ liệu (như code web).

3 Thay đổi index.html có cập nhật ngay không? Trả lời: Có, vì Docker đang đọc trực tiếp file từ ổ cứng thật thông qua Volumes.

4 Tại sao dùng hậu tố :ro? Trả lời: Để bảo vệ file cấu hình Nginx, không cho phép Container chỉnh sửa file đó (Read-Only).

5 Cloudflare Tunnel có cần mở cổng không? Trả lời: Không. Tunnel tạo kết nối ngược từ trong máy ra ngoài, giúp máy bạn "ẩn" khỏi các cuộc tấn công quét cổng từ Internet.
