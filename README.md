# Hướng dẫn cài đặt và chạy web JobsFinder

👉🏻[Source code JOBSFINDER (GGDrive)](https://drive.google.com/drive/folders/1G4IsGq0D_QKfLlEt_Mcxxl4W5B-pjZ3u?usp=drive_link)
👉🏻[Source code JOBSFINDER (github)](https://github.com/ThucTapChuyenMon/TTCM_JobsFinder)

<!-- download -->
## Tải xuống project

Tải source code của project từ Google Drive [Google Drive](https://drive.google.com/drive/folders/1G4IsGq0D_QKfLlEt_Mcxxl4W5B-pjZ3u?usp=drive_link)
Tải source code của project từ Google Drive [github](https://github.com/ThucTapChuyenMon/TTCM_JobsFinder)

<!-- installation -->
### Cài đặt CSDL

1. Tải và giải nén project
2. Mở thư mục "Database", sao đó copy 2 file vào trong đường dẫn sau: C:\Program Files\Microsoft SQL Server\<Tên server>\MSSQL\DATA
3. Mở SQL Serevr Management và kết nối vào CSDL
4. Chuột phải Database > Attach.. > Add > Chọn JobsFinder.mdf > OK > OK
5. Reload để kiểm tra csdl


## Cài đặt project.
1. Vào thư mục JobsFinder_Main, có 1 file tên là "JobsFinder_Main.snl". mở file này bằng visual studio 2022 (Hoặc phiên bản khác nếu có)

2. Thay đổi chuỗi connectionString trong App.config va trong web.config, cần thay đổi tên server, tên đăng nhập và mật khẩu đăng nhập.

```
<connectionStrings>
	<add name="JobsFinderDbContext" connectionString="data source=(Tên server);initial catalog=JobsFinder;user id=(Tên đăng nhập);password=(Mật khẩu);MultipleActiveResultSets=True;App=EntityFramework" providerName="System.Data.SqlClient" />
</connectionStrings>
```
3. Nếu không có tên máy chủ và mật khẩu bạn có thể thử đoạn mã sau:
```
<connectionStrings>
    <add name="JobsFinderDbContext" connectionString="data source=(Tên máy chủ);initial catalog=JobsFinder;Integrated Security=True;MultipleActiveResultSets=True;App=EntityFramework" providerName="System.Data.SqlClient" />
</connectionStrings>
```
3. Khởi chạy dự án bằng trình duyệt.

## Thiết lập cơ bản
### Trang quản trị

Sau khi đã khởi thành công thì ta có thể vào trtang quản trị với đường dẫn sau: https://localhost:PORT/

Với PORT là cổng truy cập trên máy local.

* Đường dẫn trang Admin
https://localhost:44300/Admin/Login.  với trang này được cấp cho 1 tài khoản là **admin** và mật khẩu là **123**


### Trang dành cho client
* Mặc định trang dành cho cient là: https://localhost:PORT/
* Người dùng có thể tạo 1 tài khoản và bắt đầu sử dụng web bình thường
