# BÁO CÁO BÀI TẬP 04: KHAI THÁC N8N ĐỂ TỰ ĐỘNG ĐĂNG BÀI LÊN WORDPRESS

**Môn học:** Phát triển ứng dụng với mã nguồn mở - TEE0421  
**Sinh viên thực hiện:** Nguyễn Thị Hằng Nga  
**Lớp:** 58KTPM  
**MSSV:** K225480106050  
**Tên miền cấu hình:** hangnga23.io.vn  

---

## 1. Công nghệ sử dụng trong hệ thống
Hệ thống tích hợp quy trình tự động hóa bao gồm 5 dịch vụ (Microservices) cốt lõi:
- **Docker & Docker Compose:** Đóng gói và quản lý vòng đời toàn bộ hệ thống trên môi trường Ubuntu.
- **MariaDB (với Image: mariadb:latest):** Hệ quản trị cơ sở dữ liệu lưu trữ toàn bộ dữ liệu cấu hình và bài viết của WordPress.
- **phpMyAdmin (với Image: phpmyadmin:latest):** Công cụ giao diện Web giúp kiểm tra, quản lý cơ sở dữ liệu trực quan.
- **WordPress (với Image: wordpress:latest):** Hệ quản trị nội dung mã nguồn mở (CMS), nơi lưu trữ và hiển thị các bài viết được xuất bản.
- **n8n (với Image: n8nio/n8n:latest):** Công cụ trung tâm xử lý quy trình tự động hóa (Workflow Automation) dựa trên sự kiện kích hoạt.
- **Cloudflare Tunnel (với Image: cloudflare/cloudflared:latest):** Giải pháp mạng an toàn giúp public 3 dịch vụ nội bộ (WordPress, phpMyAdmin, n8n) ra ngoài Internet thông qua giao thức HTTPS bảo mật mà không cần mở cổng mạng (Port Forwarding).

---

## 2. Các bước triển khai hệ thống

### Bước 2.1: Triển khai và cập nhật file `docker-compose.yml`
Sử dụng kết quả hạ tầng sẵn có từ Bài tập 03 tại đường dẫn `/mnt/d/wordpress_docker` trên Ubuntu, thực hiện chỉnh sửa cấu hình bằng trình soạn thảo `nano` để tích hợp thêm service `n8n` và dịch vụ chạy ngầm của `cloudflared`.Thực hiện lệnh khởi chạy các container chạy ngầm trong hệ thống:

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/59ad25dd-47fc-4ec8-a130-d4c55632b4a0" />

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/51ffa7d0-9ee8-486b-b015-e643a4aae170" />

Bash
sudo docker-compose up --detach
Kiểm tra trạng thái hoạt động để đảm bảo các dịch vụ chạy ổn định, không bị lỗi lặp lại vòng lặp restart liên tục:

<img width="1460" height="265" alt="image" src="https://github.com/user-attachments/assets/b2d529b0-84a8-4c9e-a834-5af641f22520" />

Bash
sudo docker-compose ps

<img width="1466" height="205" alt="image" src="https://github.com/user-attachments/assets/744c4c7c-cd8a-45a7-97c7-9f68501fd92a" />

### Bước 2.2: Cấu hình Add Routers trên Cloudflare Tunnel Dashboard
Truy cập vào giao diện quản lý Cloudflare Zero Trust, chuyển đến cấu hình đường dẫn mạng của Tunnel và thêm 3 Public Hostname tương ứng nhằm ánh xạ các Port nội bộ của Container ra ngoài Internet:

web.hangnga23.io.vn trỏ về địa chỉ nội bộ: http://wordpress:80

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/ebbe52af-e739-4881-bcba-a4f8c304d495" />

pma.hangnga23.io.vn trỏ về địa chỉ nội bộ: http://phpmyadmin:80

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/295fdc00-9e09-46ff-b6c7-7e19f0d863da" />

k58-n8n.hangnga23.io.vn trỏ về địa chỉ nội bộ: http://n8n:5678

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/ef5459e3-1b68-4d71-ae7c-57bac831c65d" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/cb41b219-e14b-4ddf-b3e0-9e3771c432e5" />


### Bước 2.3: Kiểm tra Cơ sở dữ liệu và hoàn tất thiết lập WordPress
Kiểm tra trạng thái ban đầu: Đăng nhập vào trang quản trị cơ sở dữ liệu thông qua liên kết công khai https://pma.hangnga23.io.vn. Truy cập cơ sở dữ liệu wordpress, ghi nhận ban đầu cấu trúc dữ liệu hoàn toàn trống (không chứa bất kỳ bảng nào).

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/bd98fb19-527a-492a-a95e-943bcc94cbc2" />


Khởi tạo mã nguồn: Truy cập đường dẫn https://web.hangnga23.io.vn và thực hiện các bước cấu hình cài đặt ban đầu cho WordPress. Sau khi cài đặt hoàn tất, tiến hành tải lại giao diện phpMyAdmin, hệ thống tự động sinh ra cấu trúc các bảng quản trị nội dung.

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/30e4945d-d458-4b5c-aae5-d38eab82d928" />


### Bước 2.4: Tạo các bài đăng thủ công yêu cầu trên Website
Sử dụng tài khoản Quản trị vừa tạo đăng nhập vào https://web.hangnga23.io.vn/wp-admin tiến hành soạn thảo và xuất bản 2 bài viết mẫu:

Bài viết số 1: Giới thiệu thông tin cá nhân sinh viên Nguyễn Thị Hằng Nga - Lớp 58KTPM, MSSV K225480106050, kèm theo nội dung mô tả các sở thích cá nhân độc đáo như nghe nhạc từ nhóm K-pop BTS và theo đuổi xu hướng tập luyện bộ môn Pickleball. Bài đăng được định dạng hiển thị sinh động kết hợp hình ảnh đa phương tiện.

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/daf9e4c5-bfae-4a21-9ee8-28e290aa9e83" />


<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/26dbcdc8-f978-4227-a815-5ca90196ad1c" />


Bài viết số 2: Tổng hợp và tóm tắt toàn bộ khối lượng kiến thức lý thuyết và thực hành đã thu hoạch được qua các buổi học của học phần Phát triển ứng dụng với mã nguồn mở (Các lệnh quản trị Docker cơ bản, cách thiết lập Docker Compose mạng nội bộ cô lập, giải pháp định tuyến Cloudflare Tunnel).

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/77717d2c-ab8f-4051-ac09-1ec13acf198a" />


## 3. Quy trình cấu hình và xây dựng luồng tự động hóa n8n
### Bước 3.1: Kích hoạt License n8n Community Edition
Đăng nhập giao diện https://k58-n8n.hangnga23.io.vn, tiến hành tạo tài khoản quản trị hệ thống bằng email cá nhân.

Khai báo thông tin tại form đăng ký License Key để hệ thống n8n gửi chuỗi mã bản quyền về email.

Điều hướng đến góc trái màn hình: chọn mục Settings -> Usage and plan -> Enter activation key -> Dán chuỗi ký tự nhận được và kích hoạt thành công phiên bản mở rộng Community Edition.

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/1c5555d0-bb8d-4d6f-9c88-800780ae28be" />


### Bước 3.2: Thiết lập chìa khóa API kết nối bên ngoài
Telegram API: Chat trực tiếp với @BotFather trên ứng dụng Telegram bằng lệnh /newbot để sinh ra một con Bot điều khiển độc lập của riêng mình. Lưu trữ chuỗi ký tự Access Token bảo mật được cấp. Đồng thời, tìm kiếm và kích hoạt trò chuyện lần đầu (/start) với Bot để mở luồng kết nối sự kiện sự kiện chat.

Google Gemini AI API: Truy cập cổng Google AI Studio (https://aistudio.google.com/api-keys), khởi tạo dự án mới và trích xuất chuỗi mã API KEY phục vụ cho tác vụ điều khiển xử lý ngôn ngữ tự nhiên.

### Bước 3.3: Xây dựng biểu đồ liên kết Workflow Automation trên n8n
Tạo một Workflow trống mới và cấu hình nối tiếp tuần tự 4 khối xử lý (Nodes) chức năng:

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/d158d8f5-b143-4134-971f-be141b2c9950" />


### 1. Khối kích hoạt: Node Telegram Trigger (OnMessage)
Chọn cấu hình Credential dạng tạo mới, điền chuỗi Token bảo mật nhận từ BotFather.

Thiết lập hành động lắng nghe sự kiện: OnMessage (Bất cứ khi nào người dùng nhắn tin, luồng quy trình lập tức khởi động).

### 2. Khối Trí tuệ nhân tạo: Node Google Gemini AI (Message a model)
Cấu hình xác thực thông qua API Key lấy từ Google AI Studio.

Thiết lập Model lõi thực thi: gemini-1.5-flash.

Tại phần thông tin Prompt, trỏ đường dẫn biến động lấy giá trị từ tin nhắn Telegram {{ $json.message.text }} kết hợp kèm theo một chuỗi câu lệnh ràng buộc kỹ thuật:

. Hãy viết một bài viết hoàn chỉnh dựa trên yêu cầu trên. Kết quả trả về DUY NHẤT dưới dạng một chuỗi JSON (Strict JSON object), không bọc trong các ký tự markdown \``json. Cấu trúc JSON bắt buộc phải chính xác như sau: {"post_title": "Tiêu đề bài viết", "post_content": "Toàn bộ nội dung bài viết định dạng chuẩn cấu trúc HTML+CSS để tối ưu giao diện hiển thị trên WordPress"}`

Kích hoạt tùy chọn: Turn on Output Content as JSON thiết lập giá trị thành ON.

Thiết lập tùy chọn bổ sung nâng cao tại trường System Message nhằm kiểm soát chặt chẽ dữ liệu đầu ra: "Bạn là một chuyên gia nội dung số. Bạn chỉ được phép trả về chuỗi đối tượng JSON thô chính xác, tuyệt đối không chèn thêm bất kỳ văn bản giải thích phụ nào ngoài cấu trúc."

### 3. Khối lọc dữ liệu: Node Code (JavaScript)
Dữ liệu sinh ra từ mô hình AI cần được chuẩn hóa định dạng cấu trúc dữ liệu trước khi nạp vào hệ thống API WordPress. Đoạn code JavaScript dưới đây bóc tách chính xác hai giá trị tiêu đề và nội dung bài viết:

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/a5b99f68-fa97-4fad-b3a1-932e5009af86" />

### 4. Khối xuất bản: Node WordPress (Create a Post)
Tạo khóa định danh: Truy cập giao diện bảng quản trị https://web.hangnga23.io.vn/wp-admin -> mục Thành viên (Users) -> Chọn tài khoản Admin hiện hành -> Kéo xuống phần cấu hình Mật khẩu ứng dụng (Application Passwords) -> Nhập nhãn gợi nhớ n8n và khởi tạo mã. Hệ thống cấp một chuỗi mã bảo mật gồm 24 ký tự riêng biệt.

Cấu hình khối trên n8n:

Ô địa chỉ URL đích: https://web.hangnga23.io.vn/

Hình thức xác thực (Authentication): Chọn Basic Auth (Sử dụng tên tài khoản WordPress kèm Mật khẩu ứng dụng vừa tạo).

Tùy chọn bỏ qua cảnh báo chứng chỉ: Ignore SSL Issues (Insecure) gạt nút thành ON.

Liên kết dữ liệu động: Tại trường Title, liên kết biểu thức lấy dữ liệu từ node Code phía trước: {{ $json.title }}. Tại trường Content, liên kết biểu thức: {{ $json.content }}.

Bấm nút chọn Add Field, cấu hình thuộc tính trạng thái xuất bản Status đặt giá trị mặc định là Publish (Website tự động xuất bản bài đăng ngay lập tức, không lưu ở mục Bản nháp).

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/9913713a-b970-47cb-a4d5-ec039e8b6b9b" />

## 4. Kiểm thử vận hành thực tế hệ thống tự động hóa
Tiến hành nhấn nút Publish kích hoạt trạng thái chạy ngầm thực tế cho Workflow trên n8n.

Thực hiện nhắn tin từ ứng dụng Telegram trên thiết bị di động đến tài khoản Bot với nội dung yêu cầu bài viết: "Viết một bài giới thiệu về các lợi ích nổi bật của việc ứng dụng mã nguồn mở trong doanh nghiệp công nghệ thông tin hiện nay".

Hệ thống ghi nhận chuỗi sự kiện được kích hoạt tự động hóa tuần tự qua các node. Truy cập giao diện trang chủ https://web.hangnga23.io.vn và thực hiện F5 tải lại trang, ghi nhận bài viết mới xuất bản thành công với tiêu đề tự động và nội dung bao gồm mã nhúng HTML/CSS giao diện đẹp mắt.

<img width="1170" height="2532" alt="image" src="https://github.com/user-attachments/assets/aa21494f-e33e-4f92-a74e-dcdec80c67ba" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/73be036c-c8a1-432c-a837-a2bc297fac72" />


[ DÁN ẢNH MÀN HÌNH BÀI VIẾT ĐÃ LÊN SÓNG TỰ ĐỘNG TRÊN WEB WORDPRESS TẠI ĐÂY ]

## 5. Đánh giá và nhận xét thành quả đạt được
### 5.1. Ưu điểm nổi bật của kiến trúc hệ thống
Tính tự động hóa cao và linh hoạt: Giải pháp giúp rút gọn toàn bộ quy trình viết bài, biên tập nội dung, dàn trang, tạo mã màu định dạng thiết kế và đăng tải lên CMS chỉ thông qua một tin nhắn văn bản ngắn từ xa bằng thiết bị di động mà không cần đăng nhập trang quản trị.

Khả năng kiểm soát dữ liệu hiệu quả: Khối trung gian xử lý bằng ngôn ngữ lập trình JavaScript kết hợp các điều kiện lọc (Clean chuỗi Markdown) giúp hệ thống loại bỏ triệt để các lỗi xung đột cú pháp dữ liệu cấu trúc khi nhận phản hồi từ Mô hình AI (Gemini).

Môi trường hạ tầng tối ưu và an toàn: Việc đóng gói toàn bộ quy trình và kết nối mạng thông qua Docker Compose kết hợp Cloudflare Tunnel giúp hệ thống triển khai nhanh chóng, dễ dàng mở rộng và bảo mật thông tin an toàn nhờ giao thức HTTPS tự động mã hóa.

### 5.2. Hạn chế và hướng phát triển trong tương lai
Sự phụ thuộc vào định dạng đầu ra của AI: Nếu mô hình Gemini trả về cấu trúc chuỗi JSON bị lỗi cú pháp nặng (ví dụ thiếu dấu ngoặc nhọn, dấu phẩy cấu trúc), node JavaScript có thể gặp lỗi phân tách chuỗi dữ liệu (JSON Parsing Error). Do đó, cần bổ sung thêm các node xử lý rẽ nhánh điều kiện logic (If/Switch Node) hoặc cơ chế tự động gửi lại Prompt để xử lý lỗi (Retry Logic) giúp tăng tính ổn định bền vững cho hệ thống tự động hóa nội dung trong tương lai.

---
