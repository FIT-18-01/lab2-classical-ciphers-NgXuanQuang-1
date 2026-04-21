# Test Cases – FIT4012 Lab 2

## Caesar Cipher

- [x] Encrypt `I LOVE YOU` với key `3` → `L ORYH BRX`
- [x] Encrypt `hello world` với key `5` → `mjqqt btwqi`
- [x] Decrypt `LORYH BRX` với key `3` → `I LOVE YOU`
- [x] Encrypt `cryptography` với key `2` → `etarvqitahmd`
- [x] Decrypt `etarvqitahmd` với key `2` → `cryptography`

## Rail Fence Cipher

- [x] Encrypt `I LOVE YOU` với `2` rails → `ILV O OEYU`
- [x] Encrypt `I LOVE YOU` với `4` rails → `I EYLOV OOU`
- [x] Decrypt `ILV O OEYU` với `2` rails → `I LOVE YOU`
- [x] Decrypt `I EYLOV OOU` với `4` rails → `I LOVE YOU`
- [x] Encrypt `hello` với `3` rails → `hloel`

## Validation / File input

- [x] Kiểm tra đầu vào không hợp lệ: báo lỗi "Invalid input. Only letters and spaces are allowed."
- [x] Đọc thông điệp từ `data/input.txt` và mã hóa thành công
