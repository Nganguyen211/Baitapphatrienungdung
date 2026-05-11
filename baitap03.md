# BÁO CÁO BÀI TẬP: HỆ THỐNG QUẢN LÝ TIỆM CẦM ĐỒ

**Sinh viên thực hiện:** Nguyễn Thị Hằng Nga

**Lớp:** 58KTPM 

**MSSV:** K225480106050

--

# Công nghệ sử dụng

- Docker
- Docker Compose
- MariaDB
- phpMyAdmin
- WordPress
- Cloudflare Tunnel

---

# Các bước thực hiện

## 1Tạo thư mục project

Lệnh 

mkdir wordpress-docker

cd wordpress-docker

## 2. Tạo file docker-compose.yml

Lệnh 

nano docker-compose.yml

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/45d93bd0-bbe1-4784-a9e1-abeedd7dbb09" />


---
sudo docker compose up -d

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/b421f31f-d7f6-452a-9c55-2bfb616e5270" />



sudo docker ps

Mở WordPress

Trên Ubuntu mở trình duyệt:

http://localhost:8000
## 3. Cài WordPress
Mục       --         Nội dung

SiteTitle  :    	Website cá nhân

Username	   :        admin

Password	   :       admin123

Email	   :       email của bạn

=>Bấm: Install WordPress
(Chèn ảnh)

Mở phpMyAdmin

http://localhost:8080

Đăng nhập:

Mục	-- Giá trị

Username : root

Password	: root123

Server để mặc định hoặc nhập: mariadb

---

## 4. Tạo bài viết

(Chèn ảnh)

---

## 5. Public website

(Chèn ảnh)

---

# Nhận xét

## Ưu điểm
- Dễ triển khai
- Có giao diện quản trị
- Nhiều plugin

## Nhược điểm
- Tốn RAM nếu dùng nhiều plugin
- Cần bảo mật tốt
- WordPress khá nặng

## Đánh giá cá nhân
WordPress phù hợp để xây dựng website nhanh mà không cần code quá nhiều.
