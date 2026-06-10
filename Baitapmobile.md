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

## III. THỰC HÀNH SÁNG TẠO: APP 1 (Dữ liệu Offline từ Assets)
### 1. Sinh viên tự đặt ra vấn đề và giải quyết

Bài toán: Xây dựng ứng dụng "Cẩm nang tra cứu số điện thoại của sinh viên trường TNUT dành cho sinh viên 58KTP".

Đặc thù dữ liệu: Dữ liệu được cấu trúc dưới dạng file văn bản danhba_tnut.txt cất trong thư mục assets. Mỗi dòng chứa thông tin: Tên Sinh viên - Số Điện Thoại.

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
