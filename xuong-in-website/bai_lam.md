# BÀI LÀM – HACKATHON 02

- **Mã đề:** 06
- **Họ tên:** Nguyễn Việt Dũng
- **Lớp:** HNKS26CNTT3
- **Link repository:** [GitHub](https://github.com/nguyenvietdung122008-boop-DungVN/HN_HSK26_-CNTT3-_nhapmon-cntt_hackathon02)
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
PS C:\dung\starter-kit\xuong-in-website> pwd
PS C:\dung\starter-kit\xuong-in-website> ls
PS C:\dung\starter-kit\xuong-in-website> Move-Item -Path "yeu_cau_khach_hang.txt" -Destination "docs"
PS C:\dung\starter-kit\xuong-in-website> mkdir "backup"
PS C:\dung\starter-kit\xuong-in-website>  copy-item "data\don_in_thang_6.xlsx" "backup\don_in_thang_6.xlsx"
PS C:\dung\starter-kit\xuong-in-website> Remove-Item "*.tmp"
PS C:\dung\starter-kit\xuong-in-website> cd "logs"
PS C:\dung\starter-kit\xuong-in-website\logs> cd..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
( Directory: C:\dung\starter-kit\xuong-in-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  11:05 AM                backup
d-----        11/11/2026  10:58 AM                data
d-----        11/11/2026  11:05 AM                docs
d-----        11/11/2026  10:55 AM                evindence
d-----        11/11/2026  10:58 AM                logs
d-----        11/11/2026  10:48 AM                web
------         11/3/2026   7:07 AM             76 .env
-a----         11/3/2026   7:07 AM           2407 bai_lam.md


    Directory: C:\dung\starter-kit\xuong-in-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/11/2026  10:49 AM          11329 don_in_thang_6.xlsx


    Directory: C:\dung\starter-kit\xuong-in-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        11/11/2026  10:49 AM          11329 don_in_thang_6.xlsx


    Directory: C:\dung\starter-kit\xuong-in-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            153 yeu_cau_khach_hang.txt


    Directory: C:\dung\starter-kit\xuong-in-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            981 order.log


    Directory: C:\dung\starter-kit\xuong-in-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:48 AM                images
------         11/3/2026   7:07 AM            594 app.js
------         11/3/2026   7:07 AM            516 index.html
------         11/3/2026   7:07 AM            460 style.css


    Directory: C:\dung\starter-kit\xuong-in-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:07 AM           3092 logo-printnow.png
)
```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
cat .\logs\order.log | Select-String "status=500" > .\logs\loi_500.txt
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-06-28 08:15:01 POST /api/thanh-toan status=500
2026-06-28 08:34:07 POST /api/tai-file status=500
```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
 (cat .\logs\order.log | Select-String "status=404").count
```

```text
4
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\tong_hop.ps1
```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-06-28 08:08:39 GET /mau-tet-cu status=404
2026-06-28 08:19:12 GET /images/poster-2.jpg status=404
2026-06-28 08:23:23 GET /images/poster-2.jpg status=404
2026-06-28 08:54:24 GET /tin-tuc status=404




Count    : 6
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | Console | ERR_FILE_NOT_FOUND, hienThiSanPham is not defined | Sửa lại đường dẫn/tên file/tên biến trong index.html |
| 2 | Network | logo.jpg | Sửa lại đường dẫn/tên file trong index.html |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).


### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Lỗi logo không hiển thị, bảng giá không hiển thị
- **Expected:** Web chạy tốt không hiển thị thông báo lỗi
- **Actual:** Web chưa được sửa, đang cần phía backend sửa lại lỗi
- **Log:** ERR_FILE_NOT_FOUND, hienThiSanPhan is not defined

### Câu tìm kiếm Google

```text
site:stackoverflow.com "ERR_FILE_NOT_FOUND"
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_in_thang_6.xlsx`, không cần ghi vào đây.
