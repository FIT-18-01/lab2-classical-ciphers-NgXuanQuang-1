# Report 1 Page – FIT4012 Lab 2

## 1. Mục tiêu

Bài lab nhằm giúp sinh viên hiểu và cài đặt hai mã hóa cổ điển: Caesar Cipher và Rail Fence Cipher. Sinh viên sẽ:

- Cài đặt Caesar Cipher với hỗ trợ chữ thường, giữ dấu cách, và giải mã
- Cài đặt Rail Fence Cipher với khả năng mã hóa, giải mã, giữ dấu cách, kiểm tra đầu vào, và đọc dữ liệu từ file
- Làm quen với quy trình kiểm thử, ghi log và quản lý dự án bằng GitHub

## 2. Cách làm

- Hoàn thiện hàm `caesar_encrypt()` để xử lý chữ hoa, chữ thường và giữ khoảng trắng
- Hoàn thiện hàm `caesar_decrypt()` bằng cách đảo ngược phép dịch chuyển
- Hoàn thiện hàm `rail_fence_encrypt()` để mã hóa theo kiểu zigzag
- Cài đặt hàm `rail_fence_decrypt()` bằng cách tái tạo kiểu zigzag và lấy ký tự theo thứ tự đúng
- Triển khai hàm `read_message_from_file()` để đọc dữ liệu từ file `data/input.txt`
- Kiểm tra các trường hợp đầu vào không hợp lệ và báo lỗi thích hợp

## 3. Kết quả chính

### 3.1 Caesar Cipher

| Input       | Key | Ciphertext / Plaintext | Nhận xét                            |
| ----------- | --: | ---------------------- | ----------------------------------- |
| I LOVE YOU  |   3 | L ORYH BRX             | Mã hóa thành công, giữ khoảng trắng |
| hello world |   5 | mjqqt btwqi            | Hỗ trợ chữ thường hoàn toàn         |
| LORYH BRX   |   3 | I LOVE YOU             | Giải mã chính xác (shift ngược)     |

### 3.2 Rail Fence Cipher

| Input      | Rails | Ciphertext / Plaintext | Nhận xét                                |
| ---------- | ----: | ---------------------- | --------------------------------------- |
| I LOVE YOU |     2 | ILV O OEYU             | Mã hóa theo kiểu zigzag với 2 ray       |
| I LOVE YOU |     4 | I EYLOV OOU            | Mã hóa với 4 ray, khoảng trắng được giữ |
| ILV O OEYU |     2 | I LOVE YOU             | Giải mã thành công                      |

### 3.3 Input validation / file input

- Trường hợp đầu vào không hợp lệ: Chương trình báo lỗi "Invalid input. Only letters and spaces are allowed." khi nhập ký tự đặc biệt
- Kết quả đọc từ `data/input.txt`: Đọc thành công thông điệp `I LOVE YOU` và mã hóa được tùy theo số ray được chỉ định

## 4. Kết luận

Qua bài lab này, em đã hiểu rõ hơn về hai mã hóa cổ điển và cách triển khai chúng bằng C++. Khó khăn lớn nhất là cài đặt hàm giải mã cho Rail Fence Cipher vì cần phải tính toán chính xác vị trí của từng ký tự trong kiểu zigzag. Tuy nhiên, bằng cách vẽ sơ đồ, em đã hiểu được cách tính toán và cài đặt được hàm giải mã. Bài lab giúp em thấy rõ mối liên hệ giữa lý thuyết toán học và thực hành lập trình, cũng như cách xử lý các trường hợp đặc biệt (như khoảng trắng và các ký tự khác nhau).
