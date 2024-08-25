### ** Điều Hướng Trong Cisco IOS Command Line (thêm)**

Trong phần này, chúng ta sẽ khám phá cách làm việc với dòng lệnh trên hệ điều hành Cisco IOS, cụ thể là cách sử dụng lịch sử lệnh, chỉnh sửa lệnh, và điều hướng qua các chế độ khác nhau. Tôi sẽ giải thích chi tiết các lệnh được sử dụng và hiển thị kết quả đầu ra để bạn có thể hiểu rõ hơn về cách thức hoạt động của chúng.

#### **1. Sử Dụng Lịch Sử Lệnh (Command History)**

Khi làm việc với Cisco IOS, bạn có thể cần truy xuất lại các lệnh đã sử dụng trước đó mà không cần phải nhập lại toàn bộ lệnh. Đây là nơi mà lịch sử lệnh trở nên hữu ích.

**Ví dụ:**

```bash
Router(config)# ip host Server1 192.168.1.10
Router(config)# ip host Server2 192.168.1.11
```

Trong ví dụ này, tôi đã nhập hai lệnh để thêm các mục host với địa chỉ IP tương ứng. Bây giờ, tôi sẽ đổi tên thiết bị (hostname), nhưng cố tình mắc lỗi.

```bash
Router(config)# Router1
```

**Kết quả:**

```bash
% Invalid input detected at '^' marker.
```

Lỗi này xảy ra vì tôi đã quên nhập từ khóa `hostname` trước tên mới `Router1`.

**Sửa lỗi bằng lịch sử lệnh:**

Thay vì nhập lại toàn bộ lệnh, bạn có thể nhấn phím mũi tên lên (↑) để truy xuất lệnh trước đó, sau đó sử dụng tổ hợp phím `Ctrl + A` để di chuyển con trỏ về đầu dòng, và nhập từ khóa `hostname`:

```bash
Router(config)# hostname Router1
```

**Kết quả:**

```bash
Router1(config)#
```

Như bạn thấy, dấu nhắc lệnh đã thay đổi để phản ánh tên mới của router là `Router1`.

#### **2. Sử Dụng Lệnh 'do' trong Global Configuration Mode**

Một trong những vấn đề phổ biến mà người mới bắt đầu gặp phải là cố gắng chạy các lệnh hiển thị (như `show`) trong chế độ cấu hình toàn cục (Global Configuration Mode). Tuy nhiên, những lệnh này chỉ khả dụng trong chế độ đặc quyền (Privileged EXEC Mode).

**Ví dụ:**

```bash
Router1(config)# show ip interface brief
```

**Kết quả:**

```bash
% Invalid input detected at '^' marker.
```

Để giải quyết vấn đề này mà không cần thoát khỏi chế độ cấu hình, bạn có thể sử dụng lệnh `do` trước lệnh `show`:

```bash
Router1(config)# do show ip interface brief
```

**Kết quả:**

```bash
Interface              IP-Address      OK? Method Status                Protocol
FastEthernet0/0        192.168.1.1     YES manual up                    up
FastEthernet0/1        unassigned      YES unset  administratively down down
```

Như bạn thấy, việc sử dụng `do` cho phép bạn thực hiện lệnh `show` mà không cần rời khỏi chế độ cấu hình.

#### **3. Chế Độ Cấu Hình Giao Diện (Interface Configuration Mode)**

Khi bạn muốn cấu hình một giao diện cụ thể trên router, bạn cần chuyển sang chế độ cấu hình giao diện (Interface Configuration Mode). 

**Ví dụ:**

```bash
Router1(config)# interface FastEthernet0/0
Router1(config-if)# ip address 192.168.1.1 255.255.255.0
Router1(config-if)# no shutdown
```

**Kết quả:**

```bash
Router1(config-if)#
```

Ở đây, tôi đã cấu hình địa chỉ IP cho giao diện `FastEthernet0/0` và kích hoạt nó với lệnh `no shutdown`.

#### **4. Điều Hướng Giữa Các Chế Độ**

Trong Cisco IOS, bạn có thể di chuyển giữa các chế độ khác nhau bằng cách sử dụng các lệnh như `exit`, `end`, và `Ctrl+C`.

- **Lệnh `exit`:** Giúp bạn thoát khỏi một cấp độ và quay lại cấp độ trước đó.

  ```bash
  Router1(config-if)# exit
  Router1(config)#
  ```

- **Lệnh `end`:** Giúp bạn thoát khỏi chế độ cấu hình và quay lại chế độ đặc quyền (Privileged EXEC Mode).

  ```bash
  Router1(config)# end
  Router1#
  ```

- **Tổ hợp phím `Ctrl + C`:** Tương tự như lệnh `end`, cho phép bạn thoát nhanh về chế độ đặc quyền.

#### **5. Các Lệnh 'show' Thường Dùng**

Hai lệnh `show` phổ biến mà bạn sẽ sử dụng rất nhiều khi làm việc với Cisco IOS là `show ip interface brief` và `show running-config`.

- **`show ip interface brief`:** Hiển thị trạng thái của các giao diện và địa chỉ IP được cấu hình.

  ```bash
  Router1# show ip interface brief
  ```

  **Kết quả:**

  ```bash
  Interface              IP-Address      OK? Method Status                Protocol
  FastEthernet0/0        192.168.1.1     YES manual up                    up
  FastEthernet0/1        unassigned      YES unset  administratively down down
  ```

- **`show running-config`:** Hiển thị toàn bộ cấu hình hiện tại của router.

  ```bash
  Router1# show running-config
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

  Để tìm kiếm một phần cụ thể trong cấu hình, bạn có thể sử dụng các tùy chọn `pipe`:

  ```bash
  Router1# show running-config | include interface
  ```

  **Kết quả:**

  ```bash
  interface FastEthernet0/0
  interface FastEthernet0/1
  ```

  Lệnh trên chỉ hiển thị các dòng trong cấu hình có chứa từ `interface`.

### **Tổng Kết**

Các chế độ trong Cisco IOS cung cấp nhiều cách để điều hướng và cấu hình thiết bị mạng. Việc nắm vững cách sử dụng lịch sử lệnh, chuyển đổi giữa các chế độ, và thực hiện các lệnh hiển thị sẽ giúp bạn làm việc hiệu quả hơn với Cisco IOS.
