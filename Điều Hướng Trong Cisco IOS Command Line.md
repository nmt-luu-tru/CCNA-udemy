### Hướng Dẫn Điều Hướng Trong Cisco IOS Command Line

Trong bài học này, bạn sẽ học cách điều hướng và sử dụng các lệnh trong giao diện dòng lệnh của Cisco IOS. Đây là kỹ năng cơ bản nhưng rất quan trọng đối với các kỹ sư mạng. 
### **Kịch Bản:**
Bạn vừa mở hộp một router Cisco mới, kết nối cáp console, và đã cấp nguồn cho router. Router này hiện đang trong quá trình khởi động.

Khi router khởi động lần đầu tiên, bạn sẽ thấy câu hỏi:

```bash
Would you like to enter the initial configuration dialogue? [yes/no]:
```

Nếu bạn trả lời `yes`, hệ thống sẽ đưa bạn qua một wizard hướng dẫn bạn từng bước cấu hình thiết bị. Tuy nhiên, thông thường, bạn sẽ chọn `no` để tự cấu hình theo cách riêng của mình. Sau khi bỏ qua cấu hình tự động, các giao diện của router sẽ bắt đầu hoạt động và bạn sẽ được đưa đến dấu nhắc lệnh user exec mode.

### **User Exec Mode:**
User exec mode là chế độ cơ bản nhất với một tập hợp các lệnh hạn chế. Để xem danh sách các lệnh có sẵn trong chế độ này, bạn có thể gõ:

```bash
Router> ?
```

Kết quả sẽ hiển thị:

```bash
Exec commands:
  connect    Open a terminal connection
  disconnect Disconnect an existing network connection
  enable     Turn on privileged commands
  exit       Exit from the EXEC
  ping       Send echo messages
  show       Show running system information
  telnet     Open a telnet connection
  traceroute Trace route to destination
```

Dấu chấm hỏi `?` sẽ hiển thị tất cả các lệnh khả dụng ở chế độ này. Nếu danh sách quá dài và bạn không thể xem hết, bạn có thể cuộn xuống bằng cách nhấn phím Enter từng dòng một hoặc nhấn phím cách Spacebar để cuộn xuống từng trang.

### **Enable Mode (Privileged Exec Mode):**
Để truy cập vào nhiều lệnh hơn và thực hiện các thay đổi trên thiết bị, bạn cần chuyển sang chế độ Enable Mode. Bạn có thể làm điều này bằng cách gõ lệnh sau:

```bash
Router> enable
```

Sau khi gõ lệnh `enable`, dấu nhắc lệnh sẽ thay đổi từ `>` sang `#`, biểu thị rằng bạn đang ở chế độ Enable Mode. Chế độ này cung cấp nhiều quyền hơn để cấu hình và truy xuất thông tin thiết bị.

```bash
Router#
```

Nếu bạn muốn quay trở lại user exec mode, chỉ cần gõ lệnh:

```bash
Router# disable
```

Dấu nhắc lệnh sẽ quay lại:

```bash
Router>
```

### **Sử Dụng Viết Tắt Lệnh:**
Trong Cisco IOS, bạn có thể sử dụng viết tắt của các lệnh để tiết kiệm thời gian. Ví dụ, thay vì gõ đầy đủ lệnh `enable`, bạn có thể gõ:

```bash
Router> en
```

Và nhấn Enter. Tương tự, nếu bạn muốn gõ lệnh `disable`, bạn có thể gõ:

```bash
Router# disa
```

Lưu ý rằng viết tắt lệnh chỉ hoạt động nếu không có lệnh nào khác bắt đầu bằng cùng các chữ cái đó.

### **Lệnh `show`:**
Lệnh `show` rất hữu ích để lấy thông tin về trạng thái và cấu hình của thiết bị. Bạn có thể sử dụng lệnh `show` như sau:

```bash
Router# show ?
```

Kết quả sẽ hiển thị các tùy chọn có sẵn cho lệnh `show`:

```bash
Router# show ?
  aaa              Show AAA values
  access-lists     List access lists
  arp              Display ARP table
  ...
  version          System hardware and software status
  vlan             VTP VLAN status
```

Dấu cách sau `show` và dấu `?` sẽ hiển thị tất cả các lệnh con của `show` mà bạn có thể sử dụng. Điều này gọi là “context-sensitive help” và rất hữu ích khi bạn cần tìm hiểu thêm về các lệnh khả dụng.

### **Hoàn Thành Tự Động (Tab Completion):**
Khi bạn gõ một phần của lệnh và nhấn phím Tab, Cisco IOS sẽ tự động hoàn thành lệnh cho bạn nếu chỉ có một lệnh duy nhất bắt đầu bằng các ký tự đó. Ví dụ:

```bash
Router# show run
```

Sau đó nhấn phím Tab, hệ thống sẽ hoàn thành thành:

```bash
Router# show running-config
```

Điều này giúp bạn gõ lệnh nhanh hơn và giảm thiểu lỗi chính tả.

### **Xử Lý Lỗi Nhập Lệnh:**
Nếu bạn nhập sai lệnh, hệ thống sẽ báo lỗi. Ví dụ, nếu bạn gõ sai lệnh:

```bash
Router# show aa cct-stop-cache
```

Hệ thống sẽ trả về lỗi:

```bash
% Invalid input detected at '^' marker.
```

Dấu `^` chỉ ra vị trí chính xác trong lệnh nơi xảy ra lỗi. Bạn có thể sử dụng phím `↑` (Up Arrow) để quay lại lệnh trước và chỉnh sửa lỗi mà không cần phải nhập lại từ đầu.

### **Global Configuration Mode:**
Để thực hiện các thay đổi cấu hình trên router hoặc switch, bạn cần vào chế độ Global Configuration. Bạn làm điều này bằng cách gõ:

```bash
Router# configure terminal
```

Hoặc viết tắt là:

```bash
Router# conf t
```

Dấu nhắc lệnh sẽ thay đổi thành:

```bash
Router(config)#
```

Điều này cho thấy bạn đang ở chế độ Global Configuration.

### **Các Lệnh Đặc Biệt:**
Khi bạn đang trong chế độ Global Configuration và muốn xem thông tin, bạn có thể gặp lỗi nếu cố gắng sử dụng lệnh `show` trực tiếp. Thay vì nhận được thông tin, bạn có thể nhận được lỗi "Invalid input detected." Để giải quyết, bạn có thể thêm từ `do` trước lệnh `show` như sau:

```bash
Router(config)# do show running-config
```

Kết quả sẽ hiển thị cấu hình hiện tại của router:

```bash
Building configuration...

Current configuration : 1033 bytes
!
version 15.2
service timestamps debug datetime msec
service timestamps log datetime msec
...
```

### **Kết Luận:**
Đây là phần hướng dẫn chi tiết về cách điều hướng trong Cisco IOS Command Line. Bạn đã học cách sử dụng các lệnh cơ bản, viết tắt lệnh, và các mẹo để xử lý lỗi. Trong phần tiếp theo, chúng ta sẽ đi sâu hơn vào các lệnh cấu hình và cách quản lý cấu hình trên các thiết bị Cisco.
