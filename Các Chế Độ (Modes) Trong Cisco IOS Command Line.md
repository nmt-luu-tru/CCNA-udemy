### **Giới Thiệu Về Các Chế Độ (Modes) Trong Cisco IOS Command Line**

Cisco IOS (Internetwork Operating System) cung cấp một số chế độ (modes) khác nhau để người dùng tương tác với thiết bị. Mỗi chế độ cho phép người dùng thực hiện một tập hợp các lệnh khác nhau, từ việc kiểm tra thông tin trạng thái của hệ thống đến việc cấu hình chi tiết thiết bị. Dưới đây là giải thích chi tiết về các chế độ chính trong Cisco IOS.

### **1. User EXEC Mode (Chế Độ EXEC Người Dùng)**
- **Mô tả:** Đây là chế độ đầu tiên bạn truy cập khi bạn đăng nhập vào thiết bị. Chế độ này chỉ cung cấp một tập hợp giới hạn các lệnh, chủ yếu để kiểm tra trạng thái của hệ thống mà không thể thực hiện thay đổi cấu hình.
- **Dấu nhắc lệnh:** `Router>`
- **Lệnh phổ biến:** 
  - `show`: Hiển thị thông tin cơ bản như trạng thái giao diện hoặc cấu hình hệ thống.
  - `ping`: Kiểm tra kết nối mạng với một địa chỉ IP khác.
  - `exit`: Thoát khỏi phiên làm việc hiện tại.

**Ví dụ:**

```bash
Router> show version
```

**Kết quả:**

```bash
Cisco IOS Software, C2600 Software (C2600-ADVSECURITYK9-M), Version 12.4(15)T10, RELEASE SOFTWARE (fc3)
Technical Support: http://www.cisco.com/techsupport
...
```

### **2. Privileged EXEC Mode (Chế Độ EXEC Đặc Quyền)**
- **Mô tả:** Đây là chế độ bạn truy cập khi bạn nhập lệnh `enable` từ User EXEC Mode. Chế độ này cung cấp quyền truy cập vào nhiều lệnh hơn, bao gồm cả những lệnh cho phép bạn kiểm tra cấu hình chi tiết và thực hiện một số tác vụ quản trị.
- **Dấu nhắc lệnh:** `Router#`
- **Lệnh phổ biến:**
  - `show`: Cung cấp thông tin chi tiết hơn so với User EXEC Mode.
  - `debug`: Cho phép bạn theo dõi hoạt động của thiết bị trong thời gian thực.
  - `configure terminal`: Chuyển sang chế độ cấu hình toàn cục (Global Configuration Mode).
  - `copy running-config startup-config`: Lưu cấu hình hiện tại vào cấu hình khởi động.

**Ví dụ:**

```bash
Router# show running-config
```

**Kết quả:**

```bash
Building configuration...

Current configuration : 1033 bytes
!
version 15.2
service timestamps debug datetime msec
service timestamps log datetime msec
...
```

### **3. Global Configuration Mode (Chế Độ Cấu Hình Toàn Cục)**
- **Mô tả:** Chế độ này cho phép bạn thực hiện các thay đổi cấu hình đối với toàn bộ hệ thống. Bạn vào chế độ này từ Privileged EXEC Mode bằng cách sử dụng lệnh `configure terminal`.
- **Dấu nhắc lệnh:** `Router(config)#`
- **Lệnh phổ biến:**
  - `hostname [name]`: Đổi tên của thiết bị.
  - `interface [type] [number]`: Chuyển sang chế độ cấu hình giao diện để cấu hình một giao diện cụ thể.
  - `ip route [destination] [mask] [next-hop]`: Thêm một tuyến tĩnh vào bảng định tuyến.

**Ví dụ:**

```bash
Router(config)# hostname MyRouter
```

**Kết quả:**

```bash
MyRouter(config)#
```

### **4. Interface Configuration Mode (Chế Độ Cấu Hình Giao Diện)**
- **Mô tả:** Đây là chế độ mà bạn có thể cấu hình các giao diện mạng (như Ethernet, Serial, v.v.) trên thiết bị. Bạn vào chế độ này từ Global Configuration Mode bằng cách sử dụng lệnh `interface`.
- **Dấu nhắc lệnh:** `Router(config-if)#`
- **Lệnh phổ biến:**
  - `ip address [address] [mask]`: Đặt địa chỉ IP cho giao diện.
  - `shutdown`: Tắt giao diện.
  - `no shutdown`: Mở giao diện.

**Ví dụ:**

```bash
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
```

**Kết quả:**

```bash
Router(config-if)#
```

### **5. Sub-Interface Configuration Mode (Chế Độ Cấu Hình Giao Diện Con)**
- **Mô tả:** Sử dụng để cấu hình các giao diện con (sub-interface) trên một giao diện vật lý. Đây là chế độ con của Interface Configuration Mode.
- **Dấu nhắc lệnh:** `Router(config-subif)#`
- **Lệnh phổ biến:**
  - `encapsulation dot1Q [vlan-id]`: Cấu hình gói tin với VLAN ID.
  - `ip address [address] [mask]`: Đặt địa chỉ IP cho giao diện con.

**Ví dụ:**

```bash
Router(config-if)# interface FastEthernet0/0.1
Router(config-subif)# encapsulation dot1Q 10
Router(config-subif)# ip address 192.168.10.1 255.255.255.0
```

**Kết quả:**

```bash
Router(config-subif)#
```

### **6. Line Configuration Mode (Chế Độ Cấu Hình Đường Truyền)**
- **Mô tả:** Chế độ này cho phép bạn cấu hình các đường truyền vật lý (ví dụ như console, SSH, hoặc Telnet).
- **Dấu nhắc lệnh:** `Router(config-line)#`
- **Lệnh phổ biến:**
  - `password [password]`: Đặt mật khẩu cho đường truyền.
  - `login`: Kích hoạt yêu cầu đăng nhập bằng mật khẩu.
  - `exec-timeout [minutes] [seconds]`: Cấu hình thời gian chờ không hoạt động cho đường truyền.

**Ví dụ:**

```bash
Router(config)# line vty 0 4
Router(config-line)# password cisco123
Router(config-line)# login
```

**Kết quả:**

```bash
Router(config-line)#
```

### **7. ROMMON Mode (Chế Độ ROM Monitor)**
- **Mô tả:** ROMMON (ROM Monitor) là chế độ khôi phục và chẩn đoán khi router không thể khởi động bình thường. Chế độ này cung cấp một tập hợp rất hạn chế các lệnh chủ yếu để khắc phục sự cố khởi động và khôi phục cấu hình hệ thống.
- **Dấu nhắc lệnh:** `rommon >`
- **Lệnh phổ biến:**
  - `confreg`: Cấu hình các tham số khởi động.
  - `boot`: Khởi động thiết bị từ một hình ảnh cụ thể.
  - `set`: Xem các biến môi trường hiện tại.

**Ví dụ:**

```bash
rommon > confreg 0x2142
```

**Kết quả:**

```bash
You must reset or power cycle for new config to take effect
```

### **Tổng Kết**
Mỗi chế độ trong Cisco IOS Command Line có một tập hợp các lệnh riêng biệt và cung cấp các chức năng khác nhau. Việc hiểu rõ các chế độ này và cách chuyển đổi giữa chúng là rất quan trọng để quản lý và cấu hình thiết bị mạng Cisco một cách hiệu quả.
