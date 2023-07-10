# Forensics

## Tin học văn phòng cơ bản 

### Solution

[Đề bài]( https://drive.google.com/file/d/1WrLFE5qA-qJ6iLEQYQqCo0Xb99Yz8mTH/view?usp=drive_link)

### Solve 

Đây là một file doc có sử dụng Macro, vậy nên ta sử dụng tool có tên Olevba để kiểm tra file thôi (phương pháp đơn giản nhất)

![for](https://raw.githubusercontent.com/KongSugoi/WU-Cookie-arena-2023/main/Picture/for_1.png)

Đọc đoạn mã Macro (hơi dài) nhưng lại có một cái message ghi luôn flag => Submit thôi

```**CHH{If_u_w4nt_1_will_aft3rnull_u}**```

# Steganography

## CutieK1tty

### Solution

[Đề bài]( https://drive.google.com/file/d/18iGHuowoRUsWqwNmnuWqrqsHbMLwBJG_/view?usp=drive_link )

### Solve

Chúng ta kiểm tra ảnh được tải về với tool [Aperisolve](https://www.aperisolve.com/) thì thấy được 2 password, có thể sẽ dùng trong thời gian tới (vì hiện tại chưa biết dùng làm gì)

![steg](https://raw.githubusercontent.com/KongSugoi/WU-Cookie-arena-2023/main/Picture/steg_1.png)

Tôi dùng exiftool (được tích hợp ở Aperisolve) thì có một dòng warning là có data nào đó ở sau PNG IEND chunk

![steg](https://raw.githubusercontent.com/KongSugoi/WU-Cookie-arena-2023/main/Picture/steg_2.png)

Điều này chứng tỏ, ảnh này chính là một file zip chứa thông tin, tôi đổi phần mở rộng của file thành zip và extract, được 2 file khác

![steg](https://raw.githubusercontent.com/KongSugoi/WU-Cookie-arena-2023/main/Picture/steg_3.png)

Mở thử file y0u_4r3_cl0s3.rar thì được thông báo lỗi không thể mở do bị hỏng, vậy nên tôi thử xem mã hex của nó bằng Hxd

![steg](https://raw.githubusercontent.com/KongSugoi/WU-Cookie-arena-2023/main/Picture/steg_4.png)

Nhìn thấy signature của file bị sai (định dạng đúng phải là ```52 61 72 21 == Rar!```) nên tôi sửa và lưu lại file, mở ra và thấy có 1 file cần mật khẩu 

Thử dùng mật khẩu ban đầu mà mình tìm được ```cookiehanhoan và sp3ctrum_1s_y0ur_fr13nd``` thì thấy được ```sp3ctrum_1s_y0ur_fr13nd``` là mật khẩu đúng, mở file và lấy được flag được mã hóa base64 => giải mã và ta có được flag

```**CHH{f0r3n51cs_ma5t3r}**```
