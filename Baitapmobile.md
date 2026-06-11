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
  <img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/da89fbeb-b2ae-40f9-b9aa-c785e77ac637" />


### Bước 2: Lập trình logic bằng các khối (Blocks)

#### 1. Bản chất của việc kéo thả khối lệnh (Blocks)
Bản chất của việc lập trình khối là lắp ghép các đoạn mã lệnh đã được đóng gói sẵn dưới dạng hình họa có các rãnh khớp nhau. Nếu lắp sai logic, các khối sẽ không khít, giúp người lập trình không bao giờ bị sai cú pháp (như thiếu dấu chấm phẩy, viết sai tên hàm).

* **Ưu điểm:** Trực quan, dễ học, tốc độ làm app nhanh, không sợ lỗi chính tả khi gõ code.
* **Nhược điểm:** Khi ứng dụng có quá nhiều chức năng, số lượng khối lệnh lớn sẽ gây rối mắt, khó quản lý và không tối ưu được hiệu năng sâu như viết code thật.

#### 2. Tính năng Chiếc ba lô (Backpack)
Chiếc ba lô (nằm ở góc trên bên phải màn hình Blocks) là công cụ dùng để sao chép dữ liệu. Khi muốn copy một cụm khối lệnh từ màn hình này sang màn hình khác, ta chỉ cần kéo cụm khối đó thả vào ba lô. Sang màn hình mới, mở ba lô ra và kéo khối đó ra ngoài làm việc (tương tự như tính năng Copy - Paste).

#### 3. Sơ đồ các khối lệnh trong ứng dụng:
* **Khối chuyển màn hình tại Screen1:** Khi bấm `btnToan` thì gọi hàm mở màn hình `Screen2`. Khi bấm `btnWeb` thì mở màn hình `Screen3`.
* **Khối tính toán tại Screen2:** Lấy giá trị từ `txtA` và `txtB` để kiểm tra điều kiện: Nếu a = 0 và b = 0 thì báo vô số nghiệm; nếu a = 0 và b \neq 0 thì vô nghiệm; ngược lại nghiệm x = -b/a
* **Hình ảnh minh họa các khối lệnh (Blocks):**
  
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/91643230-0967-4568-b830-30f45b14c21e" />

<img width="1170" height="2532" alt="image" src="https://github.com/user-attachments/assets/2ad60e2c-4205-4dc2-9eac-4bab033e8200" />

<img width="1170" height="2532" alt="image" src="https://github.com/user-attachments/assets/9aa7478f-a014-4dcb-97da-0d74b7baa966" />

<img width="1170" height="2532" alt="image" src="https://github.com/user-attachments/assets/de41fae9-70b4-485a-910e-51afee711977" />

<img width="1170" height="2532" alt="image" src="https://github.com/user-attachments/assets/e5aa1152-b898-402f-b7ca-a5d60fc6a93a" />

<img width="1170" height="2532" alt="image" src="https://github.com/user-attachments/assets/01e42d86-6c45-4c3a-be42-5e5f757d4dea" />

---

## PHẦN 2: VIẾT ỨNG DỤNG TRÊN ANDROID STUDIO

### 1. Tìm hiểu các thành phần cốt lõi của Android

#### File `AndroidManifest.xml` là gì?
Đây là file cấu hình bắt buộc của mọi app Android. Nó khai báo cho hệ điều hành biết ứng dụng này gồm những màn hình nào, tên là gì. Đặc biệt, khi app muốn sử dụng các tính năng hệ thống như Internet, ta bắt buộc phải khai báo xin quyền ở file này.
* **Cú pháp xin quyền Internet:**
  ```xml
  <uses-permission android:name="android.permission.INTERNET" />
  

Để hệ điều hành Android cho phép App mở cổng kết nối mạng. Nếu không khai báo, App sẽ bị điện thoại chặn lại và văng (crash) lập tức khi gọi mạng.

#### Vòng đời của 1 ứng dụng và hàm onCreate
- Vòng đời: Một màn hình App từ lúc mở lên đến lúc tắt đi sẽ trải qua các giai đoạn: Khởi tạo (onCreate) ➔ Hiển thị (onStart) ➔ Tương tác (onResume) ➔ Tạm dừng (onPause) ➔ Bị ẩn (onStop) ➔ Bị xóa khỏi bộ nhớ (onDestroy).

- Tại sao có sẵn hàm onCreate? Vì đây là hàm khởi đầu bắt buộc. Khi bạn bấm vào icon App, điện thoại sẽ gọi hàm này đầu tiên để nạp giao diện XML (setContentView) và chuẩn bị các linh kiện bên trong. Không có nó, App không thể hình thành.

#### Kiểm tra quyền chủ động (Runtime Permission) trong Java
Code kiểm tra quyền (Ví dụ quyền đọc bộ nhớ):

```
if (ContextCompat.checkSelfPermission(this, Manifest.permission.READ_EXTERNAL_STORAGE) 
        != PackageManager.PERMISSION_GRANTED) {
    // Nếu chưa có quyền -> Hiện bảng xin người dùng cấp quyền
    ActivityCompat.requestPermissions(this, new String[]{Manifest.permission.READ_EXTERNAL_STORAGE}, 101);
}
```
Ý nghĩa: Bảo vệ quyền riêng tư của người dùng. App muốn dùng gì phải hỏi rõ ràng tại thời điểm chạy, tránh việc App chạy ngầm ăn cắp dữ liệu.

#### Quản lý giao diện bằng XML (res/layout)
a. Cơ chế tham chiếu tránh viết chữ trực tiếp (Hardcode)
Thay vì gõ trực tiếp chữ lên nút bấm, ta lưu chữ đó vào file res/values/strings.xml:

Cú pháp trong strings.xml: <string name="btn_giai">Giải Toán</string>

Cú pháp tham chiếu ở file giao diện XML: android:text="@string/btn_giai"

Cú pháp gọi bằng code Java: getString(R.string.btn_giai);

Ưu điểm: Dễ sửa (sửa 1 chỗ trong file string là toàn App đổi theo).

Hỗ trợ tự động (Auto-fetch): Hệ điều hành sẽ tự động nhận diện:

Nếu máy đổi sang tiếng Anh (LANGUAGE/LOCATION) ➔ Tự nạp file tiếng Anh.

Nếu máy bật chế độ ban đêm (THEME) ➔ Tự nạp màu tối.
➔ Giúp App làm được điều gì? Giúp App tự động thích ứng với mọi cài đặt của người dùng trên thế giới mà lập trình viên không cần viết code kiểm tra thủ công.

b. Đối tượng chứa (LinearLayout)
Dùng để gom các linh kiện con (Nút bấm, ô nhập) xếp kề nhau theo quy luật:

android:orientation="vertical": Xếp thẳng hàng từ trên xuống dưới (chiều dọc).

android:orientation="horizontal": Xếp thẳng hàng từ trái sang phải (chiều ngang).

android:gravity="center": Căn toàn bộ nội dung bên trong ra chính giữa.

#### Code tương tác với Layout (Hiển thị text tránh hardcode)
Trong Java, muốn hiển thị chữ đáp ứng đúng ngôn ngữ máy của người dùng:

```Java
TextView myText = findViewById(R.id.txtHienThi);
myText.setText(R.string.welcome_text); // Tham chiếu tới file strings.xml, không gõ thẳng chữ vào đây
```
#### Xử lý sự kiện người dùng (Click Button)
Giao diện LAYOUT cần làm gì? Cần đặt cho nút bấm một cái tên (ID) định danh: android:id="@+id/btnNutBam".

CODE Java viết như nào? (2 Cách phổ biến):

Cách 1: Dùng lớp nặc danh (Anonymous) - Hay dùng nhất

``` Java
Button btn = findViewById(R.id.btnNutBam);
btn.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // Code chạy khi bấm nút viết ở đây
    }
});
```
Cách 2: Khai báo ngay trong thuộc tính XML

Ở file XML thêm dòng: android:onClick="xuLyClick"

Ở file Java viết hàm:

```Java
public void xuLyClick(View v) {
    // Code chạy khi bấm nút viết ở đây
}
```
#### Thư mục đặc biệt Assets
Cơ chế: Khi copy file vào thư mục này, lúc biên dịch (compiler), các file sẽ được đóng gói nguyên vẹn đi theo App vào trong điện thoại.

Cú pháp truy cập trong Java: InputStream is = getAssets().open("ten_file.txt");

Lợi ích: Dữ liệu nằm sẵn trong máy nên không có mạng (Offline) vẫn chạy mượt mà, tốc độ load cực nhanh.

## III. THỰC HÀNH SÁNG TẠO:
### APP 1 (Dữ liệu Offline từ Assets)
### 1. Sinh viên tự đặt ra vấn đề và giải quyết

Bài toán: Xây dựng ứng dụng "Cẩm nang tra cứu số điện thoại của sinh viên trường TNUT dành cho sinh viên 58KTP".

Đặc thù dữ liệu: Dữ liệu được cấu trúc dưới dạng file văn bản danhba_tnut.txt cất trong thư mục assets. Mỗi dòng chứa thông tin: Tên Sinh viên - Số Điện Thoại.
```
Nguyễn Thị Hằng Nga - 0912345678
Trần Văn Anh - 0987654321
Lê Hoàng Hải - 0905112233
Phạm Minh Đức - 0977889900
Vũ Thùy Linh - 0944556677
```
Thuật toán xử lý: Khi App mở lên, Java sẽ đọc file từ thư mục assets, sử dụng thuật toán cắt chuỗi (hàm split("-")) để phân tách tên và số điện thoại riêng ra.

Đối tượng hiển thị: Dùng ListView (hoặc RecyclerView) để hiển thị danh sách dạng danh bạ lên màn hình gọn gàng.

### Mã nguồn triển khai chi tiết trên Android Studio
a. File cấu hình giao diện hiển thị: activity_main.xml
Giao diện ứng dụng sử dụng cấu trúc LinearLayout làm đối tượng chứa bao bọc, sắp xếp các thành phần con theo chiều dọc (vertical), bao gồm một thẻ tiêu đề ứng dụng và một thành phần ListView để hiển thị danh sách.

```XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/txtTieuDe"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="DANH BẠ SINH VIÊN LỚP 58KTPM - TNUT"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="#0055A5"
        android:gravity="center"
        android:layout_marginBottom="16dp"/>

    <ListView
        android:id="@+id/lvDanhBa"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:divider="#CCCCCC"
        android:dividerHeight="1dp" />

</LinearLayout>
```
b. File xử lý logic thuật toán: MainActivity.java
Đoạn code chịu trách nhiệm thiết lập vòng đời màn hình trong hàm onCreate(), gọi tiến trình mở file từ hệ thống Assets, thực thi cắt tách chuỗi văn bản và nạp lên giao diện thông qua ArrayAdapter.

``` Java
package com.example.appdanhbatnut; // Thay thế bằng tên gói thực tế của dự án của bạn

import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.List;

public class MainActivity extends AppCompatActivity {

    private ListView lvDanhBa;
    private List<String> danhSachHienThi;
    private ArrayAdapter<String> boDieuPhoiAdapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Ánh xạ đối tượng ListView từ layout XML sang code Java
        lvDanhBa = findViewById(R.id.lvDanhBa);

        // Khởi tạo danh sách mảng động để chứa dữ liệu sau xử lý
        danhSachHienThi = new ArrayList<>();

        // Thực thi hàm gọi thuật toán đọc và phân tách chuỗi dữ liệu trong Assets
        docVaTienXuLyDuLieuAssets();

        // Cấu hình ArrayAdapter chuẩn để đồng bộ hóa dữ liệu chuỗi lên giao diện dòng phẳng
        boDieuPhoiAdapter = new ArrayAdapter<>(
                this, 
                android.R.layout.simple_list_item_1, 
                danhSachHienThi
        );

        // Đổ toàn bộ dữ liệu từ bộ điều phối lên đối tượng chứa hiển thị
        lvDanhBa.setAdapter(boDieuPhoiAdapter);
    }

    /**
     * Thuật toán đọc file văn bản từ kho Assets, cắt chuỗi bằng hàm split() để bóc tách thông tin
     */
    private void docVaTienXuLyDuLieuAssets() {
        try {
            // Mở luồng kết nối trực tiếp đến file văn bản đặt trong thư mục assets
            InputStream luongInput = getAssets().open("danhba_tnut.txt");
            BufferedReader boDocBoDem = new BufferedReader(new InputStreamReader(luongInput, "UTF-8"));
            
            String tungDongVanBan;
            // Tiến hành vòng lặp đọc dữ liệu tuần tự theo từng dòng cho đến hết file
            while ((tungDongVanBan = boDocBoDem.readLine()) != null) {
                
                // Áp dụng quy luật lọc: Kiểm tra dòng văn bản có chứa ký tự phân tách "-" hay không
                if (tungDongVanBan.contains("-")) {
                    // Sử dụng thuật toán cắt chuỗi split() để phân tách thành mảng thành phần
                    String[] mangThanhPhan = tungDongVanBan.split("-");
                    String tenSinhVien = mangThanhPhan[0].trim(); // Phần tử 0: Họ và tên sinh viên
                    String soDienThoai = mangThanhPhan[1].trim(); // Phần tử 1: Số điện thoại liên hệ

                    // Tiền xử lý định dạng chuỗi hiển thị trực quan hóa bằng biểu tượng hình họa
                    String thongTinDinhDang = "🎓 Sinh viên: " + tenSinhVien + "\n📞 Số ĐT: " + soDienThoai;
                    
                    // Nạp chuỗi thông tin hoàn chỉnh sau xử lý vào danh sách đích
                    danhSachHienThi.add(thongTinDinhDang);
                } else {
                    // Nếu dòng văn bản không chứa ký tự phân tách đặc thù, thực hiện giữ nguyên chuỗi gốc
                    danhSachHienThi.add(tungDongVanBan);
                }
            }
            
            // Đóng luồng kết nối sau khi hoàn thành chu trình xử lý để giải phóng tài nguyên hệ thống
            boDocBoDem.close();
            luongInput.close();
            
        } catch (IOException ngoaiLe) {
            ngoaiLe.printStackTrace();
            Toast.makeText(this, "Lỗi: Không thể nạp danh sách dữ liệu Offline từ Assets!", Toast.LENGTH_SHORT).show();
        }
    }
}
```
<img width="1733" height="962" alt="image" src="https://github.com/user-attachments/assets/8ee37f1e-8339-47e8-92a5-1ba306005515" />

Do thiết bị cá nhân chạy hệ điều hành iOS (iPhone) không thể kết nối trực tiếp với môi trường Android Studio, đồng thời máy tính bị giới hạn dung lượng bộ nhớ ổ đĩa để khởi chạy trình giả lập tích hợp (AVD), em đã sử dụng giải pháp Xuất file APK độc lập và kiểm thử qua nền tảng đám mây trực tuyến (Appetize.io). Quy trình triển khai gồm 3 bước:

Bước 1 (Đóng gói ứng dụng): Trên thanh công cụ Android Studio, truy cập vào menu Build ➔ Chọn Generate App Bundles or APKs ➔ Tích chọn mục APK để ép hệ thống biên dịch toàn bộ mã nguồn Java/XML thành file cài đặt app-debug.apk.

Bước 2 (Khai thác file sản phẩm): Sau khi hệ thống báo BUILD SUCCESSFUL, truy cập vào thư mục đầu ra của dự án theo đường dẫn cục bộ: D:\BaiTapLonMobile\app\build\outputs\apk\debug\ để trích xuất file app-debug.apk.

Bước 3 (Kiểm thử trực tuyến): Tải file APK đã đóng gói lên máy chủ mô phỏng đám mây Appetize.io. Hệ thống ảo hóa sẽ khởi tạo một thiết bị Android ảo chạy trực tuyến ngay trên trình duyệt web, cho phép kích hoạt và kiểm thử toàn bộ giao diện danh bạ sinh viên lớp 58KTP hoàn

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/40a1030b-d3bc-4f93-80e0-303846410c95" />
### APP 2 Giao diện như mitapp

# BƯỚC 1: KHAI BÁO THƯ VIỆN & CẤP QUYỀN INTERNET 
Vì App 2 cần gọi API gửi kết quả toán lên Server và dùng WebView tải trang web, bạn bắt buộc phải cấp quyền Internet.Cấp quyền Internet: Mở file app ➔ manifests ➔ AndroidManifest.xml. Thêm dòng sau vào ngay phía trên thẻ <application>:
```XML
<uses-permission android:name="android.permission.INTERNET" />
```
Thêm thư viện Volley (Gọi API): Nhìn xuống mục Gradle Scripts ở cây thư mục bên trái ➔ Mở file build.gradle.kts (Module :app).Tìm đến đoạn dependencies { ... } ở gần cuối file, dán thêm dòng này vào bên trong:Kotlinimplementation("com.android.volley:volley:1.2.1")

Sau khi dán xong, nhìn lên góc trên cùng bên phải màn hình sẽ hiện một thanh thông báo nhỏ, bấm nút Sync Now để tải thư viện về.
# BƯỚC 2: TẠO THÊM CÁC ACTIVITY MỚIHiện tại dự án mới chỉ có MainActivity (ta sẽ dùng làm Màn hình 1: About). 
Cần tạo thêm 2 Activity nữa:Tạo Activity 2 (Giải toán): Nhấp chuột phải vào thư mục gói code chính com.example.baitaplonmobile ➔ Chọn New ➔ Activity ➔ Empty Views Activity. Đặt tên là GiaiToanActivity rồi bấm Finish.Tạo Activity 3 (WebView): Nhấp chuột phải tiếp vào com.example.baitaplonmobile ➔ Chọn New ➔ Activity ➔ Empty Views Activity. Đặt tên là WebViewActivity rồi bấm Finish.
# BƯỚC 3: THIẾT KẾ GIAO DIỆN XML VÀ CODE JAVA CHO TỪNG MÀN HÌNH
## MÀN HÌNH 1: GIỚI THIỆU (About)Màn hình này hiển thị thông tin cá nhân của bạn và có 2 nút bấm để chuyển sang 2 màn hình còn lại.File giao diện (activity_main.xml): Xóa code cũ của App 1 đi, dán đoạn code này vào:
```XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp"
    android:background="#F5F5F5">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="THÔNG TIN SINH VIÊN"
        android:textSize="22sp"
        android:textStyle="bold"
        android:textColor="#0055A5"
        android:layout_marginBottom="20dp" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Họ và tên: Nguyễn Thị Hằng Nga\nMã số SV: (Nhập MSV của bạn vào đây)\nLớp: 58KTPM\nTrường: ĐH Kỹ thuật Công nghiệp Thái Nguyên"
        android:textSize="16sp"
        android:lineSpacingMultiplier="1.3"
        android:layout_marginBottom="40dp" />

    <Button
        android:id="@+id/btnSangGiaiToan"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Chuyển sang Giải Toán &amp; Gọi API"
        android:backgroundTint="#0055A5"
        android:layout_marginBottom="15dp" />

    <Button
        android:id="@+id/btnSangWebView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Chuyển sang Xem Trang Web"
        android:backgroundTint="#2E7D32" />
</LinearLayout>
```
File xử lý (MainActivity.java): Sửa lại để làm nhiệm vụ chuyển màn hình bằng Intent:Javapackage com.example.baitaplonmobile;
```
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btnSangGiaiToan = findViewById(R.id.btnSangGiaiToan);
        Button btnSangWebView = findViewById(R.id.btnSangWebView);

        btnSangGiaiToan.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(MainActivity.this, GiaiToanActivity.class);
                startActivity(intent);
            }
        });

        btnSangWebView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(MainActivity.this, WebViewActivity.class);
                startActivity(intent);
            }
        });
    }
}
```
## MÀN HÌNH 2: GIẢI TOÁN & GỌI API BÁO CÁO SERVER
Màn hình này sẽ giải phương trình bậc nhất ax + b = 0. Sau khi giải xong, ứng dụng tự động đóng gói dữ liệu JSON theo đúng cấu trúc và gửi lên Server bằng phương thức POST.File giao diện (activity_giai_toan.xml): Mở file này trong mục res/layout và dán code:
```
XML<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="GIẢI PHƯƠNG TRÌNH: ax + b = 0"
        android:textSize="18sp"
        android:textStyle="bold"
        android:gravity="center"
        android:layout_marginBottom="20dp"/>

    <EditText
        android:id="@+id/edtA"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Nhập hệ số a"
        android:inputType="numberDecimal|numberSigned" />

    <EditText
        android:id="@+id/edtB"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Nhập hệ số b"
        android:inputType="numberDecimal|numberSigned"
        android:layout_marginBottom="20dp"/>

    <Button
        android:id="@+id/btnGiai"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Giải và Gửi API Lên Server" />

    <TextView
        android:id="@+id/txtKetQua"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Kết quả hiển thị tại đây"
        android:textSize="16sp"
        android:textColor="#FF5722"
        android:layout_marginTop="20dp"
        android:textStyle="bold"/>
</LinearLayout>
```
File xử lý (GiaiToanActivity.java):  .Javapackage com.example.baitaplonmobile;
```
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
import com.android.volley.Request;
import com.android.volley.RequestQueue;
import com.android.volley.Response;
import com.android.volley.VolleyError;
import com.android.volley.toolbox.JsonObjectRequest;
import com.android.volley.toolbox.Volley;
import org.json.JSONException;
import org.json.JSONObject;

public class GiaiToanActivity extends AppCompatActivity {

    private EditText edtA, edtB;
    private Button btnGiai;
    private TextView txtKetQua;
    private final String MA_SV = "K225480106050"; // Hãy điền mã số sinh viên thật của bạn vào đây

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_giai_toan);

        edtA = findViewById(R.id.edtA);
        edtB = findViewById(R.id.edtB);
        btnGiai = findViewById(R.id.btnGiai);
        txtKetQua = findViewById(R.id.txtKetQua);

        btnGiai.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                thựcThiGiảiToánVàGửiAPI();
            }
        });
    }

    private void thựcThiGiảiToánVàGửiAPI() {
        String strA = edtA.getText().toString().trim();
        String strB = edtB.getText().toString().trim();

        if (strA.isEmpty() || strB.isEmpty()) {
            Toast.makeText(this, "Vui lòng nhập đầy đủ hệ số a và b!", Toast.LENGTH_SHORT).show();
            return;
        }

        double a = Double.parseDouble(strA);
        double b = Double.parseDouble(strB);
        String ketLuan = "";
        double nghiem = 0.0;

        // Thuật toán giải toán đơn giản ax + b = 0
        if (a == 0) {
            if (b == 0) {
                ketLuan = "Vô số nghiệm";
            } else {
                ketLuan = "Vô nghiệm";
            }
        } else {
            ketLuan = "Có 1 nghiệm duy nhất";
            nghiem = -b / a;
        }

        txtKetQua.setText("Kết luận: " + ketLuan + (a != 0 ? "\nNghiệm x = " + nghiem : ""));

        // Tiến hành đóng gói đối tượng JSON theo định dạng chuẩn yêu cầu của Server bộ môn
        try {
            JSONObject jsonGoc = new JSONObject();
            jsonGoc.put("app_by", MA_SV);

            // Nhóm dữ liệu đầu vào (input)
            JSONObject jsonInput = new JSONObject();
            jsonInput.put("a", a);
            jsonInput.put("b", b);
            jsonInput.put("c", 0); // Thừa hành tham số c theo định dạng cấu trúc mẫu
            jsonInput.put("name", "hello tắc kè");
            jsonGoc.put("input", jsonInput);

            // Nhóm dữ liệu đầu ra kết quả (output)
            JSONObject jsonOutput = new JSONObject();
            jsonOutput.put("ketluan", ketLuan);
            jsonOutput.put("abc", "xyz");
            jsonOutput.put("nghiem", nghiem);
            jsonGoc.put("output", jsonOutput);

            // Thực thi gửi gói tin mạng JSON lên Server qua thư viện Volley
            guiDuLieuLenServer(jsonGoc);

        } catch (JSONException e) {
            e.printStackTrace();
        }
    }

    private void guiDuLieuLenServer(JSONObject thamSoJson) {
        String urlApi = "https://k58kmt.tdh.io.vn/api";
        RequestQueue hangDoiMang = Volley.newRequestQueue(this);

        JsonObjectRequest yeuCauJson = new JsonObjectRequest(Request.Method.POST, urlApi, thamSoJson,
                new Response.Listener<JSONObject>() {
                    @Override
                    public void onResponse(JSONObject phanHoi) {
                        try {
                            // Tiếp nhận và bóc tách dữ liệu JSON nhận về từ Server thầy
                            int trangThaiOk = phanHoi.getInt("ok");
                            int soThuTuStt = phanHoi.getInt("stt");

                            Toast.makeText(GiaiToanActivity.this, 
                                    "Gửi API thành công! STT nhận về: " + soThuTuStt, 
                                    Toast.LENGTH_LONG).show();
                        } catch (JSONException e) {
                            e.printStackTrace();
                        }
                    }
                },
                new Response.ErrorListener() {
                    @Override
                    public void onErrorResponse(VolleyError error) {
                        error.printStackTrace();
                        Toast.makeText(GiaiToanActivity.this, "Lỗi kết nối hoặc sai cấu hình gọi API!", Toast.LENGTH_SHORT).show();
                    }
                });

        hangDoiMang.add(yeuCauJson);
    }
}

```

## MÀN HÌNH 3: WEB-VIEW TRUY CẬP TRANG WEB 
Màn hình này sử dụng đối tượng WebView để nhúng trực tiếp trang web chấm điểm/quản lý của hệ thống bộ môn kèm theo tham số mã sinh viên của bạn.File giao diện (activity_web_view.xml): Mở file trong mục res/layout dán đè đoạn này:
```XML
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <WebView
        android:id="@+id/wvHeThong"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
</RelativeLayout>
```
File xử lý (WebViewActivity.java): Sửa lại mã để WebView kích hoạt Javascript và tải trang web tự động:Javapackage com.example.baitaplonmobile;
```
import android.os.Bundle;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import androidx.appcompat.app.AppCompatActivity;

public class WebViewActivity extends AppCompatActivity {

    private WebView wvHeThong;
    private final String MA_SV = "K225480106050"; // Điền chính xác mã sinh viên của bạn vào đây

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_web_view);

        wvHeThong = findViewById(R.id.wvHeThong);

        // Cấu hình WebView chuẩn để mở web ngay trong nội tại ứng dụng không bị văng ra trình duyệt ngoài
        wvHeThong.setWebViewClient(new WebViewClient());
        
        WebSettings caiDatWeb = wvHeThong.getSettings();
        caiDatWeb.setJavaScriptEnabled(true); // Kích hoạt thực thi mã biên dịch Javascript của trang đích

        // Khởi tạo chuỗi định dạng URL kèm theo tham số nhận diện mã sinh viên động
        String linkCuaThay = "https://k58kmt.tdh.io.vn?masv=" + MA_SV;
        wvHeThong.loadUrl(linkCuaThay);
    }

    @Override
    public void onBackPressed() {
        // Thuật toán tối ưu trải nghiệm: Cho phép WebView lùi trang lịch sử thay vì thoát thẳng Activity
        if (wvHeThong.canGoBack()) {
            wvHeThong.goBack();
        } else {
            super.onBackPressed();
        }
    }
}
```
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/649f9b4d-577e-4bdb-b900-ecb248f7fb52" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/8a495696-a16d-4fd9-95db-9c58097d9459" />

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/22e66b5a-2468-40a4-838b-03b39c776056" />
