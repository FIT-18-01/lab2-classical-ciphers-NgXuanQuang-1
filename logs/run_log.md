# Run Log – FIT4012 Lab 2

## Caesar Cipher

- [x] Đã chạy Caesar encrypt với `I LOVE YOU`, key `3` → `L ORYH BRX`
- [x] Đã chạy Caesar encrypt với `hello world`, key `5` → `mjqqt btwqi`
- [x] Đã chạy Caesar decrypt với `LORYH BRX`, key `3` → `I LOVE YOU`
- [x] Đã chạy Caesar encrypt với `cryptography`, key `2` → `etarvqitahmd`
- [x] Đã chạy Caesar decrypt với `etarvqitahmd`, key `2` → `cryptography`

## Rail Fence Cipher

- [x] Đã chạy Rail Fence encrypt với `I LOVE YOU`, `2` rails → `ILV O OEYU`
- [x] Đã chạy Rail Fence encrypt với `I LOVE YOU`, `4` rails → `I EYLOV OOU`
- [x] Đã chạy Rail Fence decrypt `ILV O OEYU` với `2` rails → `I LOVE YOU`
- [x] Đã chạy Rail Fence decrypt `I EYLOV OOU` với `4` rails → `I LOVE YOU`
- [x] Đã chạy Rail Fence encrypt với `hello`, `3` rails

## Validation / File input

- [x] Đã kiểm tra đầu vào không hợp lệ (tín hiệu lỗi: "Invalid input. Only letters and spaces are allowed.")
- [x] Đã đọc dữ liệu từ `data/input.txt` → `I LOVE YOU`

## Điều em học được từ bài lab

Qua bài lab này, em hiểu sâu hơn về cách hoạt động của hai mã hóa cổ điển: Caesar Cipher và Rail Fence Cipher. Em nắm được cách xử lý các ký tự (chữ hoa, chữ thường, khoảng trắng) một cách chính xác. Điều khó khăn nhất là triển khai hàm giải mã cho Rail Fence Cipher, vì cần phải hiểu rõ cách các ký tự được sắp xếp theo kiểu zigzag. Nhưng sau khi vẽ sơ đồ và kiểm thử từng bước, em đã hiểu rõ và cài đặt thành công. Bài lab giúp em kết nối lý thuyết về mã hóa với thực hành lập trình.
