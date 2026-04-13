# BÁO CÁO BÀI TẬP LỚN - HỆ THỐNG WEB & DOCKER
**Sinh viên:** Nguyễn Thị Hằng Nga


# PHẦN A: ĐĂNG KÝ TÊN MIỀN & CLOUDFLARE

### 1. Đăng ký tên miền tại Mắt Bão
- Tên miền đã chọn: `yourdomain.id.vn`
- Trạng thái: Đã xác thực eKYC.
> **[DÁN ẢNH: Ảnh chụp màn hình quản trị tên miền tại Mắt Bão báo "Đang hoạt động"]**

### 2. Cấu hình DNS Cloudflare
- Đã trỏ Nameservers từ Mắt Bão sang Cloudflare.
> **[DÁN ẢNH: Ảnh chụp giao diện Nameserver tại Mắt Bão và Dashboard Cloudflare báo "Active"]**

# PHẦN B: CÀI ĐẶT UBUNTU & DOCKER

### 1. Thông tin hệ thống
- Hệ điều hành: Ubuntu 24.04 LTS (Cài trực tiếp trên ổ cứng).
- IP máy chủ: `192.168.x.x`
> **[DÁN ẢNH: Chụp Terminal lệnh `ip -4 addr`]**

### 2. Cài đặt Docker & SSH
- Đã cài đặt Docker và Docker-compose plugin.
- Đã cấu hình Group Docker để chạy không cần `sudo`.
> **[DÁN ẢNH: Chụp Terminal lệnh `docker --version` và `docker compose version`]**

### 3. Cấu hình tường lửa UFW
> **[DÁN ẢNH: Chụp lệnh `sudo ufw status` hiện các cổng 80, 1880, 9630 đang Allow]**


# PHẦN C: CẤU HÌNH DOCKER COMPOSE

### 1. Cấu trúc thư mục trên ổ D
- Đường dẫn: `/media/hangnga/DATA/myapp`
> **[DÁN ẢNH: Chụp lệnh `ls -R` hoặc cây thư mục dự án trên ổ D]**

### 2. File cấu hình Nginx & Docker-compose
> **[DÁN ẢNH: Chụp nội dung file nginx.conf và docker-compose.yml]**


# PHẦN D: BONUS - ỨNG DỤNG FLASK API

### 1. Mã nguồn API
- Ngôn ngữ: Python 3.9 Slim.
- Framework: Flask.
> **[DÁN ẢNH: Chụp nội dung file app.py và Dockerfile]**

### 2. Xây dựng Image
> **[DÁN ẢNH: Chụp quá trình Docker build image myapi]**


# PHẦN E: TRIỂN KHAI & KIỂM THỬ

### 1. Khởi chạy hệ thống
- Lệnh: `docker compose up -d`
> **[DÁN ẢNH: Chụp kết quả lệnh `docker ps` hiện 4-5 container đang Up]**

### 2. Kiểm tra các dịch vụ
- Truy cập Web cá nhân qua Localhost.
- Truy cập Node-RED qua cổng 1880.
> **[DÁN ẢNH: Chụp trình duyệt hiển thị index.html và giao diện Node-RED]**

# PHẦN F: GỠ LỖI & QUẢN LÝ TÀI NGUYÊN

### 1. Kiểm tra Logs
> **[DÁN ẢNH: Chụp lệnh `docker logs mynginx`]**

### 2. Giới hạn tài nguyên (Resources)
- Đã giới hạn RAM 512M cho service.
> **[DÁN ẢNH: Chụp lệnh `docker compose stats` hiện mức RAM sử dụng]**

# PHẦN G: TRIỂN KHAI END-USER & TRẢ LỜI CÂU HỎI

### 1. Cloudflare Tunnel
- Trạng thái Tunnel: Healthy.
- Public Hostname: `https://web.yourdomain.id.vn`
> **[DÁN ẢNH: Chụp Dashboard Cloudflare hiện Tunnel xanh (Healthy)]**
> **[DÁN ẢNH: Chụp điện thoại truy cập vào tên miền qua 4G thành công]**

### 2. Trả lời câu hỏi lý thuyết
1 Tại sao dùng Nginx làm Reverse Proxy? Trả lời: Để quản lý tập trung các dịch vụ trên cùng một cổng 80, tăng tính bảo mật và dễ dàng cấu hình SSL/TLS sau này.

2 Sự khác biệt Mount file và Mount thư mục? Trả lời: Mount file gắn kết 1 file duy nhất (như config), mount thư mục gắn kết toàn bộ folder dữ liệu (như code web).

3 Thay đổi index.html có cập nhật ngay không? Trả lời: Có, vì Docker đang đọc trực tiếp file từ ổ cứng thật thông qua Volumes.

4 Tại sao dùng hậu tố :ro? Trả lời: Để bảo vệ file cấu hình Nginx, không cho phép Container chỉnh sửa file đó (Read-Only).

5 Cloudflare Tunnel có cần mở cổng không? Trả lời: Không. Tunnel tạo kết nối ngược từ trong máy ra ngoài, giúp máy bạn "ẩn" khỏi các cuộc tấn công quét cổng từ Internet.
