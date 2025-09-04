# Phần mềm Quản lý Phòng mạch tư
Đây là bản copy từ repo nhóm (link gốc: https://github.com/QuocThang1302/Qua-n-ly-pho-ng-ma-ch).   
## 📌 Giới thiệu
Đây là đồ án môn học *Nhập môn Công nghệ Phần mềm* tại Trường Đại học Công nghệ Thông tin (UIT).  
Mục tiêu của dự án là xây dựng một hệ thống **quản lý phòng mạch tư** nhằm hỗ trợ bác sĩ, y tá và quản lý trong việc:
- Quản lý bệnh nhân, lịch khám, phiếu khám và đơn thuốc.
- Quản lý thuốc, nhân viên, lịch trực.
- Tự động tạo hóa đơn và báo cáo tháng.
- Cải thiện hiệu quả vận hành phòng khám và nâng cao trải nghiệm người dùng.

## 🛠️ Công nghệ sử dụng
- **Ngôn ngữ:** Java 17  
- **Giao diện:** JavaFX 17  
- **Cơ sở dữ liệu:** PostgreSQL 15+  
- **Kết nối DB:** JDBC (PostgreSQL Driver)  
- **IDE khuyến nghị:** IntelliJ IDEA / Eclipse  
- **Các công cụ khác:** CSS để thiết kế giao diện

## 🚀 Cài đặt & chạy phần mềm

### 1. Yêu cầu hệ thống
- Hệ điều hành: Windows 10/11, Ubuntu 20.04+, macOS 11+  
- RAM: tối thiểu 8GB (khuyến nghị 16GB)  
- Dung lượng trống: 2GB  
- JDK: 17 trở lên  
- JavaFX SDK: 17  
- PostgreSQL: 15+  

### 2. Cài đặt các thành phần
1. **Cài đặt JDK 17**  
   - [Tải JDK](https://jdk.java.net/) và cài đặt.  
   - Thiết lập biến môi trường `JAVA_HOME`.  

2. **Cài đặt JavaFX 17**  
   - [Tải JavaFX](https://gluonhq.com/products/javafx/).  
   - Giải nén và lưu lại đường dẫn (ví dụ `C:\javafx-sdk-17`).  

3. **Cài đặt PostgreSQL**  
   - [Tải PostgreSQL](https://www.postgresql.org/download/).  
   - Giữ port mặc định `5432`, tạo mật khẩu cho user `postgres`.  
   - Tạo database:
     ```sql
     CREATE DATABASE QuanLyPhongMachTu;
     ```
   - Import cấu trúc bảng:
     ```bash
     psql -U postgres -d QuanLyPhongMachTu -f "Database CNPM.sql"
     ```

4. **Import project vào IDE**  
   - Mở IntelliJ IDEA / Eclipse → Import Project.  
   - Thêm thư viện **JavaFX** và **PostgreSQL JDBC driver** (`postgresql-42.x.x.jar`).  
   - Cấu hình VM options để chạy JavaFX:
     ```
     --module-path /path/to/javafx-sdk-17/lib --add-modules javafx.controls,javafx.fxml
     ```
### 3. Chạy chương trình
- Mở project trong IDE (IntelliJ IDEA / Eclipse) và chạy.  
- Nếu cài đặt đúng, màn hình **Đăng nhập** sẽ hiển thị.  

👉 **Lưu ý:**  
Nếu muốn trải nghiệm chức năng **Quên mật khẩu**, bạn cần tạo file cấu hình email:  

1. Tạo file mới tại đường dẫn: src/main/resources/email.properties
2. Thêm thông tin tài khoản email gửi OTP:
```properties
email.username=your_email@example.com
email.password=your_app_password
```
Khuyến nghị bảo mật:
- Sử dụng App Password (mật khẩu ứng dụng) thay vì mật khẩu chính của email.
- Không commit file email.properties lên GitHub. Hãy thêm nó vào .gitignore.

### 4. Tài khoản mẫu
- **Admin:** `admin / 123456`  
- **Bác sĩ:** `doctor / 123456`  
- **Y tá:** `nurse / 123456`  
- **Quản lý:** `manager / 123456`  

## 📖 Chức năng chính
- **Admin:** Quản lý tài khoản, nhân viên, quy định, báo cáo.  
- **Bác sĩ:** Quản lý phiếu khám, lập đơn thuốc, xem lịch trực.  
- **Y tá:** Lập danh sách khám bệnh, nhập liệu, quản lý hóa đơn.  
- **Quản lý:** Phân công lịch trực, xem báo cáo doanh thu và hiệu suất.  

## 👥 Phân công công việc
Trong dự án, tôi phụ trách:
- Hỗ trờ thiết kế database và model
- Code CRUD dữ liệu
- Quản lý bệnh nhân
- Quản lý nhân viên
- Quản lý lịch khám
- Quản lý báo cáo tháng
- Lấy lại mật khẩu thông qua email
- Dashboard

## 📌 Hướng phát triển
- Tích hợp cổng thanh toán (MoMo, ZaloPay).  
- Kết nối máy in hóa đơn.  
- Mở rộng cho bệnh nhân đặt lịch online.  
- Nâng cao khả năng bảo mật và trải nghiệm người dùng.  

