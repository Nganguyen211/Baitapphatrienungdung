# BÁO CÁO BÀI TẬP LỚN
## MÔN HỌC: PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG (TEE0419)

* **Họ và tên:** Nguyễn Thị Hằng Nga
* **Mã số sinh viên:** K225480106050
* **Lớp học phần:** 58KTP


---

## PHẦN 1: TẠO PHẦN MỀM TRÊN MIT APP INVENTOR

### Bước 1: Thiết kế giao diện (Designer)
Truy cập trang web MIT App Inventor, tạo một dự án mới và thiết kế 3 màn hình (Screen) bằng cách kéo thả các thành phần từ thanh công cụ (Palette) bên trái vào màn hình điện thoại.

#### 1. Màn hình 1 (Screen1): Giới thiệu bản thân
* **Thành phần sử dụng:** * `Label`: Hiển thị họ tên, mã số sinh viên, lớp 58KTP.
  * `Image`: Hiển thị ảnh chân dung cá nhân.
  * `Button1` (đặt tên là `btnToan`): Nút bấm để mở màn hình giải toán.
  * `Button2` (đặt tên là `btnWeb`): Nút bấm để mở màn hình xem trang web.
* **Hình ảnh minh họa:**
  <img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/2fe734e9-99ea-4638-a920-22b3f610dc43" />


#### 2. Màn hình 2 (Screen2): Giải phương trình bậc nhất ax + b = 0
* **Thành phần sử dụng:**
  * 2 `TextBox` (`txtA` và `txtB`): Để người dùng nhập số a và số b
  * 1 `Button` (`btnGiai`): Người dùng bấm vào để tính kết quả.
  * 1 `Label` (`lblKetQua`): Để hiện chữ kết quả (Vô nghiệm, vô số nghiệm hoặc nghiệm x = -b/a).
* **Hình ảnh minh họa:**
  <img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/f434e3c4-b625-40ff-8464-a1718cadc148" />

#### 3. Màn hình 3 (Screen3): Hiển thị Website (WebView)
* **Thành phần sử dụng:**
  * `WebViewer`: Kéo thả vào màn hình. Tại bảng thuộc tính bên phải, mục `HomeUrl`, điền link: `https://k58kmt.tdh.io.vn?masv=[Điền_MSV_Của_Bạn]`.
* **Hình ảnh minh họa:**
  *[CHÈN ẢNH CHỤP MÀN HÌNH GIAO DIỆN SCREEN3 CỦA BẠN VÀO ĐÂY]*

---

### Bước 2: Lập trình logic bằng các khối (Blocks)

#### 1. Bản chất của việc kéo thả khối lệnh (Blocks)
Bản chất của việc lập trình khối là lắp ghép các đoạn mã lệnh đã được đóng gói sẵn dưới dạng hình họa có các rãnh khớp nhau. Nếu lắp sai logic, các khối sẽ không khít, giúp người lập trình không bao giờ bị sai cú pháp (như thiếu dấu chấm phẩy, viết sai tên hàm).

* **Ưu điểm:** Trực quan, dễ học, tốc độ làm app nhanh, không sợ lỗi chính tả khi gõ code.
* **Nhược điểm:** Khi ứng dụng có quá nhiều chức năng, số lượng khối lệnh lớn sẽ gây rối mắt, khó quản lý và không tối ưu được hiệu năng sâu như viết code thật.

#### 2. Tính năng Chiếc ba lô (Backpack)
Chiếc ba lô (nằm ở góc trên bên phải màn hình Blocks) là công cụ dùng để sao chép dữ liệu. Khi muốn copy một cụm khối lệnh từ màn hình này sang màn hình khác, ta chỉ cần kéo cụm khối đó thả vào ba lô. Sang màn hình mới, mở ba lô ra và kéo khối đó ra ngoài làm việc (tương tự như tính năng Copy - Paste).

#### 3. Sơ đồ các khối lệnh trong ứng dụng:
* **Khối chuyển màn hình tại Screen1:** Khi bấm `btnToan` thì gọi hàm mở màn hình `Screen2`. Khi bấm `btnWeb` thì mở màn hình `Screen3`.
* **Khối tính toán tại Screen2:** Lấy giá trị từ `txtA` và `txtB` để kiểm tra điều kiện: Nếu a = 0 và b = 0 thì báo vô số nghiệm; nếu a = 0 và b \neq 0 thì vô nghiệm; ngược lại nghiệm x = -b/a$.
* **Hình ảnh minh họa các khối lệnh (Blocks):**
  *[CHÈN ẢNH CHỤP MÀN HÌNH CÁC KHỐI LỆNH BLOCKS CỦA 3 SCREEN VÀO ĐÂY]*

---

## PHẦN 2: VIẾT ỨNG DỤNG TRÊN ANDROID STUDIO

### 1. Tìm hiểu các thành phần cốt lõi của Android

#### File `AndroidManifest.xml` là gì?
Đây là file cấu hình bắt buộc của mọi app Android. Nó khai báo cho hệ điều hành biết ứng dụng này gồm những màn hình nào, tên là gì. Đặc biệt, khi app muốn sử dụng các tính năng hệ thống như Internet, ta bắt buộc phải khai báo xin quyền ở file này.
* **Cú pháp xin quyền Internet:**
  ```xml
  <uses-permission android:name="android.permission.INTERNET" />
