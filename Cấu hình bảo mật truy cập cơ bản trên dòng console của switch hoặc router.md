
### Bước 1: Truy cập vào thiết bị trong Packet Tracer
1. Mở Packet Tracer và chọn switch hoặc router mà bạn muốn cấu hình.
2. Nhấp đúp vào thiết bị để mở giao diện CLI (Command Line Interface).

### Bước 2: Vào chế độ cấu hình toàn cục
1. Gõ lệnh `enable` để vào chế độ EXEC cao cấp (privileged EXEC mode).
   ```shell
   Router> enable
   ```
2. Tiếp theo, vào chế độ cấu hình toàn cục bằng lệnh `configure terminal`.
   ```shell
   Router# configure terminal
   ```

### Bước 3: Cấu hình bảo mật trên dòng console
1. Truy cập vào chế độ cấu hình của dòng console với lệnh `line console 0`.
   ```shell
   Router(config)# line console 0
   ```
   Lệnh này truy cập vào chế độ cấu hình của cổng console (line console) trên thiết bị. Số 0 chỉ ra console đầu tiên (và thường là duy nhất) của switch hoặc router.
   
3. Đặt mật khẩu cho cổng console bằng lệnh `password`, ví dụ mật khẩu là `123`.
   ```shell
   Router(config-line)# password 123
   ```
4. Bật chế độ yêu cầu nhập mật khẩu khi truy cập bằng lệnh `login`.
   ```shell
   Router(config-line)# login
   ```
5. Thoát khỏi chế độ cấu hình dòng console bằng lệnh `exit`.
   ```shell
   Router(config-line)# exit
   Router(config)# exit
   ```

### Bước 4: Lưu cấu hình
1. Lưu cấu hình vào bộ nhớ NVRAM để đảm bảo thiết bị sẽ giữ lại cấu hình sau khi khởi động lại bằng lệnh `write memory` hoặc `copy running-config startup-config`.
   ```shell
   Router# write memory
   ```
   Hoặc:
   ```shell
   Router# copy running-config startup-config
   ```

### Ví dụ cấu hình hoàn chỉnh
Dưới đây là các lệnh hoàn chỉnh bạn sẽ nhập để thiết lập bảo mật cơ bản cho cổng console trên router hoặc switch trong Packet Tracer:
```shell
Router> enable
Router# configure terminal
Router(config)# line console 0
Router(config-line)# password 123
Router(config-line)# login
Router(config-line)# exit
Router(config)# exit
Router# write memory
```

### Kiểm tra cấu hình
- Sau khi cấu hình, hãy thử ngắt kết nối console và kết nối lại. Thiết bị sẽ yêu cầu nhập mật khẩu để truy cập vào chế độ cấu hình.
