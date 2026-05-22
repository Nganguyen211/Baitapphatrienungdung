# BÁO CÁO BÀI TẬP: HỆ THỐNG VIẾT TRANG WEB

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
sudo docker compose up --detach

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/eefdb830-8159-44b8-a64b-db7ac3e369d7" />

sudo docker ps

Mở WordPress
<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/1968894f-9713-4596-915f-9ed3f7d12c8e" />

Trên Ubuntu mở trình duyệt:

http://localhost:8000

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/93d246ee-9389-4d73-a998-24a82d59b49b" />

## 3. Cài WordPress
Mục       --         Nội dung

SiteTitle  :    	Website cá nhân

Username	   :        admin

Password	   :       @

Email	   :       email của bạn

=>Bấm: Install WordPress

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/d071b66f-5cd6-4df3-b891-ced24cd1bf43" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/45c7f247-dda9-4275-8ec3-d641efee70cd" />

Mở phpMyAdmin

http://localhost:8081

Đăng nhập:

Mục	-- Giá trị

Username : root

Password	: root_password_123

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/751beae4-1c88-4ecb-a567-6f33a2645af6" />

Server để mặc định hoặc nhập: mariadb

---

## 4. Tạo bài viết
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/1a3104a7-0aa6-4947-a8cd-34c39aa3cdde" />

# bài viết số 1 

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/a45b892e-f8e2-477c-8131-75343454de01" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/874ad0bf-bbf2-4fd6-b8eb-eb17697bdac1" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/e8bc3ef8-3b09-498e-823c-e6afe0f108a2" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/2db4598a-aa29-46f6-ad1f-fdba3cc695d4" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/310a4f93-fb63-4f82-85c5-df54e471d6ef" />

# bài viết số 2

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/70f88114-1205-43e4-afe0-382e533e6661" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/975443e4-9cd1-4ec4-97be-40d36a7b10b1" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/4fd05bc6-e8ba-4186-bfc4-01a7b2e8875e" />


---

## 5. Public website

# Bước 1: Trỏ NameServer về Cloudflare (Nếu chưa làm)

Để dùng được Cloudflare Tunnel với tên miền riêng, tên miền của Nga phải được quản lý bởi Cloudflare.

Đăng nhập vào dash.cloudflare.com.

Nhấn Add a Site -> Nhập hangnga23.io.vn.

Cloudflare sẽ đưa cho bạn 2 dòng NameServer (ví dụ: gene.ns.cloudflare.com và todd.ns.cloudflare.com).

Quay lại trang Quản lý tên miền của Mắt Bão , nhấn vào Chi tiết dịch vụ của tên miền đó và tìm phần Thay đổi NameServer, dán 2 dòng của Cloudflare vào.

# Bước 2: Tạo Tunnel cố định trên Ubuntu (WSL2)

Bash
1. Tạo tunnel tên là hangnga-wp
cloudflared tunnel create hangnga-wp

<img width="1503" height="178" alt="image" src="https://github.com/user-attachments/assets/6d776f16-0e9d-487a-91e5-8491d80f83b0" />

 2. Trỏ subdomain web.hangnga23.io.vn về Tunnel hangnga-wp
    
cloudflared tunnel route dns hangnga-wp web.hangnga23.io.vn

<img width="1488" height="108" alt="image" src="https://github.com/user-attachments/assets/e378a70e-8c8e-468c-94c0-1cd8ec0db6fd" />

# Bước 4: Chạy Tunnel để Public

Bây giờ là bước quan trọng nhất để "thông" mạng từ máy tính của bạn ra tên miền thật:

4. Chạy tunnel kết nối localhost:8000 với tên miền đã cấu hình
   
cloudflared tunnel run --url http://localhost:8000 hangnga-tunne

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/063d77b8-c4f8-4f04-bfc5-4c38e3ee6c35" />

Bước 5: Cập nhật URL trong WordPress 

Khi web đã chạy trên tên miền thật, Nga cần vào WordPress Admin để đổi địa chỉ:

Truy cập http://localhost:8000/wp-admin

Vào Cài đặt (Settings) -> Tổng quan (General).

Sửa cả 2 dòng WordPress Address và Site Address thành: https://web.hangnga23.io.vn (nhớ có https).

Nhấn Lưu thay đổi.

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/efe08311-64aa-468c-a5e0-0bdd65366f3b" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/ab75df61-ff2b-4267-8443-bcf4ee5a3e39" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/c3009e50-d029-4300-bade-c2761a234f3c" />

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
