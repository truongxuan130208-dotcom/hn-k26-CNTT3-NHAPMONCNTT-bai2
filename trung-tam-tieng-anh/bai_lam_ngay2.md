# BÀI LÀM – ÔN TẬP NGÀY 2

- **Họ tên:PHẠM XUÂN TRƯỜNG**
- **Lớp:CNTTT3**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):WINDOWS**

## Bài 1. Lọc log thủ công

### Lệnh đã chạy

```shell
# PS C:\Users\tTRUONG\Downloads\starter-kit(1)\starter-kit\trung-tam-tieng-anh> GET-CONTENT .\logs\access.log | select-string "ERROR"

```

### 2 dòng lỗi đầu tiên trong error_report.txt

```text
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
```

## Bài 2. Đếm bằng pipeline

### Lệnh

```shell
# gc .\logs\access.log | Select-string "WARNING" | Measure-Object -Line
# gc .\logs\payment.log | Select-string "ERROR" | Measure-Object -Line

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
WARNING trong access.log:4
ERROR trong payment.log:3
```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\auto_warning.ps1
```

### Nội dung file logs/warning_report.txt

```text
=== CANH BAO THANH TOAN ===
2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi

```

## Bài 4. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
 gc .\logs\access.log | select-string "ERROR"
 (get-content .\logs\payment.log | select-string "WARNING").COUNT
```

### Nội dung file logs/tong_hop_ngay2.txt

```text
=== TONG HOP ACCESS LOG ===

2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)

```

## Bài 5. Câu hỏi ngắn

- **a)Lệnh ... > là chèn một nội dung vô file và xoá các nội dung trước đó đã lưu, lệnh ... >> là thêm một nội dung vô file mà không xoá nội dung trước đó**
- **b)nếu dùng > thay cho >> thì những nội dung trước đó sẽ biến mất thay bằng nội dung được chèn vô**
- **c)bởi vì mỗi cá nhân lại có một gốc khác nhau nên gửi đường dẫn tuyệt đối sẽ rất dễ bị lỗi trong khi đó đường dẫn tương đối nó chỉ quy định trong các file tài luyện mà các máy đều có và sẽ không bị lỗi không tìm thấy đường dẫn**

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
