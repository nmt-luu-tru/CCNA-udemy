
1. **Nhấp vào router để mở cửa sổ chi tiết**

2. **Chọn tab CLI:**
   - **Mục đích:** CLI (Command Line Interface) là nơi bạn nhập các lệnh để cấu hình router. Đây là giao diện chính để tương tác với thiết bị mạng bằng lệnh.
   - **Giao diện lệnh:**
     ```
     Router>
     ```
**Nếu khi bạn nhấp vào CLI của router lần đầu tiên và nhận được thông báo:**

```
Would you like to enter the initial configuration dialog? [yes/no]:
```

**Ý nghĩa:**
- Đây là một lời nhắc từ hệ thống hỏi bạn có muốn thực hiện cấu hình ban đầu cho router thông qua một trình hướng dẫn từng bước hay không. Trình hướng dẫn này giúp người dùng thiết lập các cấu hình cơ bản như tên thiết bị, mật khẩu, và các cấu hình giao diện mà không cần nhập các lệnh chi tiết.

**Lựa chọn:**
- **Chọn `no`:** Nếu bạn chọn `no`, bạn sẽ được chuyển trực tiếp vào CLI của router mà không cần qua trình hướng dẫn. Đây là lựa chọn phổ biến nếu bạn muốn thực hiện cấu hình chi tiết hoặc nếu bạn đã quen với việc sử dụng CLI để cấu hình thiết bị.
  
  - **Giao diện lệnh:**
    ```
    Would you like to enter the initial configuration dialog? [yes/no]: no
    Press RETURN to get started!
    Router>
    ```

- **Chọn `yes`:** Nếu bạn chọn `yes`, hệ thống sẽ bắt đầu hướng dẫn bạn qua từng bước cấu hình cơ bản. Điều này có thể hữu ích cho người mới bắt đầu hoặc khi bạn cần một cấu hình nhanh chóng mà không cần nhiều tùy chọn chi tiết.

  - **Giao diện lệnh:**
    ```
    Would you like to enter the initial configuration dialog? [yes/no]: yes
    (System will guide you through the setup process)
    ```

**Tóm lại:** Nếu bạn muốn thực hiện cấu hình chi tiết với quyền kiểm soát cao hơn, bạn nên chọn `no`. Nếu bạn muốn một cấu hình nhanh chóng và cơ bản, hãy chọn `yes`.  

3. **Nhập lệnh `enable` và nhấn Enter:**
   - **Mục đích:** Lệnh `enable` chuyển router từ chế độ EXEC người dùng (User EXEC mode) sang chế độ EXEC đặc quyền (Privileged EXEC mode). Chế độ này cho phép bạn truy cập vào các lệnh cao cấp hơn, bao gồm cấu hình thiết bị.
   - **Giao diện lệnh:**
     ```
     Router>enable
     Router#
     ```

4. **Nhập lệnh `configure terminal` và nhấn Enter:**
   - **Mục đích:** Lệnh này chuyển router vào chế độ cấu hình toàn cục (Global Configuration mode). Trong chế độ này, bạn có thể thực hiện các thay đổi cấu hình trên toàn hệ thống.
   - **Giao diện lệnh:**
     ```
     Router#configure terminal
     Router(config)#
     ```

5. **Nhập lệnh `interface GigabitEthernet0/0` (hoặc `FastEthernet0/0` tùy giao diện bạn đã kết nối):**
   - **Mục đích:** Lệnh này chọn giao diện mạng cụ thể để cấu hình. `GigabitEthernet0/0` hoặc `FastEthernet0/0` là tên của cổng kết nối vật lý trên router. Giao diện này kết nối với các thiết bị khác như switch hoặc máy tính.
   - **Giao diện lệnh:**
     ```
     Router(config)#interface GigabitEthernet0/0
     Router(config-if)#
     ```

6. **Nhập lệnh `ip address 192.168.1.1 255.255.255.0`:**
   - **Mục đích:** Lệnh này gán địa chỉ IP cho giao diện đã chọn. Địa chỉ IP `192.168.1.1` với subnet mask `255.255.255.0` thường được sử dụng trong mạng LAN nhỏ và cần phải nằm trong cùng subnet với các thiết bị khác như switch để chúng có thể giao tiếp với nhau.
   - **Giao diện lệnh:**
     ```
     Router(config-if)#ip address 192.168.1.1 255.255.255.0
     ```

7. **Nhập lệnh `no shutdown` để kích hoạt giao diện:**
   - **Mục đích:** Theo mặc định, các giao diện trên router thường ở trạng thái tắt (shutdown). Lệnh `no shutdown` sẽ kích hoạt giao diện, cho phép nó bắt đầu hoạt động và truyền dữ liệu.
   - **Giao diện lệnh:**
     ```
     Router(config-if)#no shutdown
     ```

8. **Nhập `exit` để quay lại chế độ cấu hình toàn cục:**
   - **Mục đích:** Lệnh `exit` thoát khỏi chế độ cấu hình giao diện cụ thể và quay lại chế độ cấu hình toàn cục, từ đó có thể tiếp tục cấu hình các thành phần khác trên router.
   - **Giao diện lệnh:**
     ```
     Router(config-if)#exit
     Router(config)#
     ```

9. **Nhập lệnh `write` hoặc `copy running-config startup-config` để lưu cấu hình:**
   - **Mục đích:** Lệnh `write` hoặc `copy running-config startup-config` lưu lại các thay đổi cấu hình bạn đã thực hiện. `running-config` là cấu hình hiện tại đang hoạt động, và `startup-config` là cấu hình sẽ được tải khi router khởi động lại. Lệnh này đảm bảo rằng khi router khởi động lại, cấu hình đã lưu sẽ được áp dụng.
   - **Giao diện lệnh:**
     ```
     Router(config)#write
     (or)
     Router(config)#copy running-config startup-config
     ```

Những lệnh này đều được thực hiện trong CLI của router và là nền tảng cơ bản để cấu hình thiết bị mạng.
