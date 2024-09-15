

## 1. **Truy cập qua Telnet**

### **Giới thiệu về Telnet**
- **Telnet** là giao thức kết nối từ xa cho phép quản trị viên truy cập và quản lý thiết bị qua mạng. 
- Hoạt động qua cổng mặc định là **23**.
- **Không mã hóa dữ liệu**, do đó dễ bị tấn công và không an toàn cho các mạng công cộng.

### **Cấu hình Telnet trên Router hoặc Switch**

1. **Cấu hình địa chỉ IP cho cổng giao diện** (giả sử cổng GigabitEthernet 0/0):
   ```shell
   Router> enable
   Router# configure terminal
   Router(config)# interface gigabitEthernet 0/0
   Router(config-if)# ip address 192.168.1.1 255.255.255.0
   Router(config-if)# no shutdown
   ```

2. **Thiết lập mật khẩu và kích hoạt Telnet trên dòng VTY:**
   ```shell
   Router(config)# line vty 0 4
   Router(config-line)# password telnet123
   Router(config-line)# login
   Router(config-line)# transport input telnet
   Router(config-line)# exit
   ```
   Giải thích:  
   ```Router(config)# line vty 0 4```  
	•	Mô tả: Lệnh này truy cập vào chế độ cấu hình của các cổng VTY (Virtual Teletype) từ 0 đến 4. VTY là các cổng ảo cho phép kết nối từ xa vào thiết bị qua các giao thức như Telnet hoặc SSH.  
	•	Ý nghĩa: Bạn đang cấu hình cho 5 cổng VTY đầu tiên (từ 0 đến 4), tức là cho phép tối đa 5 phiên kết nối từ xa đồng thời vào thiết bị.

	```Router(config-line)# password telnet123```  
	•	Mô tả: Lệnh này đặt mật khẩu telnet123 cho các cổng VTY được chọn.  
	•	Ý nghĩa: Bất kỳ ai muốn kết nối từ xa vào thiết bị qua Telnet sẽ phải nhập mật khẩu này để truy cập.

	```Router(config-line)# login```  
	•	Mô tả: Lệnh này yêu cầu thiết bị kiểm tra mật khẩu khi có ai đó cố gắng kết nối vào thiết bị qua VTY.  
	•	Ý nghĩa: Lệnh này kích hoạt yêu cầu nhập mật khẩu đã đặt (telnet123). Nếu lệnh login không được cấu hình, mật khẩu sẽ không có hiệu lực và thiết bị sẽ không yêu cầu mật khẩu khi kết nối.

	```Router(config-line)# transport input telnet```  
	•	Mô tả: Lệnh này cho phép giao thức Telnet được sử dụng để kết nối vào các cổng VTY.  
	•	Ý nghĩa: Lệnh này cấu hình cho phép các phiên Telnet kết nối vào thiết bị qua các cổng VTY được chỉ định. Nếu bạn không cấu hình transport input, các cổng VTY sẽ không nhận bất kỳ kết nối nào hoặc có thể mặc định nhận cả SSH và Telnet nếu không bị hạn chế.
 
	```Router(config-line)# exit```  
	•	Mô tả: Lệnh này thoát khỏi chế độ cấu hình cổng VTY và trở về chế độ cấu hình toàn cục (global configuration mode).  
	•	Ý nghĩa: Hoàn tất quá trình cấu hình cho các cổng VTY.  

4. **Lưu cấu hình:**
   ```shell
   Router# write memory
   ```

### **Kết nối qua Telnet từ PC**

- Mở **Command Prompt** trên PC và nhập lệnh:
   ```shell
   telnet 192.168.1.1
   ```
- Bạn sẽ được yêu cầu nhập mật khẩu (telnet123), sau khi nhập đúng, bạn sẽ truy cập vào chế độ EXEC người dùng của router hoặc switch.

### **Kết quả kiểm tra:**
- Khi kết nối thành công, bạn sẽ thấy dấu nhắc lệnh của thiết bị (ví dụ: `Router>`).
- Nếu mật khẩu sai, bạn sẽ không thể truy cập vào thiết bị.

## 2. **Truy cập qua SSH**

### **Giới thiệu về SSH**
- **SSH (Secure Shell)** là giao thức kết nối từ xa an toàn, thay thế cho Telnet, với khả năng mã hóa dữ liệu và bảo mật thông tin xác thực.
- Hoạt động qua cổng mặc định là **22**.
- Sử dụng mã hóa mạnh (thường là AES) và hỗ trợ xác thực bằng mật khẩu hoặc khóa công khai.

### **Cấu hình SSH trên Router hoặc Switch**

1. **Cấu hình địa chỉ IP cho cổng giao diện** (giả sử cổng GigabitEthernet 0/0):
   ```shell
   Router> enable
   Router# configure terminal
   Router(config)# interface gigabitEthernet 0/0
   Router(config-if)# ip address 192.168.1.1 255.255.255.0
   Router(config-if)# no shutdown
   ```

2. **Thiết lập domain name và tạo khóa mã hóa RSA cho SSH:**
   ```shell
   Router(config)# ip domain-name example.com
   Router(config)# crypto key generate rsa
   ```
   - Chọn kích thước khóa (thường là 1024 hoặc 2048 bit). Ví dụ:
   ```shell
   How many bits in the modulus [512]: 1024
   ```

3. **Tạo tài khoản người dùng và mật khẩu:**
   ```shell
   Router(config)# username admin privilege 15 secret ssh123
   ```
**Giải thích Chi Tiết Lệnh:** ```Router(config)# username admin privilege 15 secret ssh123```

```username admin```:
   - **Mô tả:** Tạo một tài khoản người dùng có tên là `admin`.
   - **Ý nghĩa:** Tên người dùng này sẽ được sử dụng khi đăng nhập vào thiết bị thông qua các giao thức như Telnet, SSH, hoặc từ console nếu yêu cầu xác thực bằng tên người dùng và mật khẩu.

```privilege 15```:
   - **Mô tả:** Thiết lập mức độ đặc quyền cho người dùng.
   - **Ý nghĩa:** 
     - Quyền `privilege 15` là mức đặc quyền cao nhất trên router hoặc switch Cisco, cho phép người dùng truy cập toàn bộ các lệnh trong chế độ EXEC cao cấp (privileged EXEC mode).
     - Người dùng với đặc quyền 15 có thể thực hiện tất cả các cấu hình và thay đổi trên thiết bị, tương tự như khi sử dụng lệnh `enable` để vào chế độ EXEC cao cấp.

```secret ssh123```:
   - **Mô tả:** Thiết lập mật khẩu cho người dùng `admin` và mã hóa mật khẩu đó bằng thuật toán mã hóa MD5.
   - **Ý nghĩa:**
     - Mật khẩu `ssh123` sẽ được mã hóa mạnh bằng MD5, không thể giải mã ngược lại thành mật khẩu gốc.
     - Sử dụng `secret` thay vì `password` giúp tăng cường bảo mật vì `secret` luôn sử dụng mã hóa mạnh (MD5) thay vì mã hóa loại 7 như `password`.

4. **Cấu hình SSH trên dòng VTY:**
   ```shell
   Router(config)# line vty 0 4
   Router(config-line)# transport input ssh
   Router(config-line)# login local
   Router(config-line)# exit
   ```

5. **Lưu cấu hình:**
   ```shell
   Router# write memory
   ```

### **Kết nối qua SSH từ PC**

- Mở **Command Prompt** hoặc một phần mềm SSH client như PuTTY trên PC và nhập lệnh:
   ```shell
   ssh -l admin 192.168.1.1
   ```
- Bạn sẽ được yêu cầu nhập mật khẩu (`ssh123`), sau khi nhập đúng, bạn sẽ truy cập vào chế độ EXEC người dùng của router hoặc switch.

### **Kết quả kiểm tra:**
- Khi kết nối thành công, bạn sẽ thấy dấu nhắc lệnh của thiết bị (ví dụ: `Router>`).
- **Nếu xác thực không thành công (mật khẩu sai), kết nối sẽ bị từ chối.**

---
## Mã hóa mật khẩu
  Thêm lệnh: ```Router(config)# service password-encryption```  
  Chú ý là chế độ (config)#.
  
