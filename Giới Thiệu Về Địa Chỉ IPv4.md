### Giới Thiệu Về Địa Chỉ IPv4

Trong bài giảng này, bạn sẽ học về cấu trúc của một địa chỉ IPv4 và cách viết chúng ra dưới dạng thập phân có dấu chấm.

#### 1. Cấu Trúc Địa Chỉ IPv4

Địa chỉ IPv4 được viết dưới dạng 4 octet trong một định dạng thập phân có dấu chấm. Một ví dụ về địa chỉ IPv4 là: **192.168.10.15**.

- Mỗi phần của địa chỉ được gọi là một **octet**.
  - **192** là octet đầu tiên.
  - **168** là octet thứ hai.
  - **10** là octet thứ ba.
  - **15** là octet thứ tư.

Mỗi octet bao gồm 8 bit, và vì vậy, tổng số bit trong một địa chỉ IPv4 là 32 bit (8 bit x 4 octet).

#### 2. Cách Xem Địa Chỉ IP Trên Các Thiết Bị

- **Trên Windows**: Bạn có thể kiểm tra địa chỉ IP bằng cách mở Command Prompt và sử dụng lệnh `ipconfig`.

  Ví dụ:
  ```bash
  C:\> ipconfig
  ```
  Kết quả trả về sẽ hiển thị địa chỉ IP của máy tính, subnet mask, và default gateway.

  ```bash
  IPv4 Address. . . . . . . . . . . : 192.168.1.9
  Subnet Mask . . . . . . . . . . . : 255.255.255.0
  Default Gateway . . . . . . . . . : 192.168.1.1
  ```

- **Trên Linux**: Bạn sử dụng lệnh `ifconfig` để xem địa chỉ IP.

  Ví dụ:
  ```bash
  $ ifconfig
  ```
  Kết quả sẽ hiển thị địa chỉ IP và subnet mask của máy chủ.

  ```bash
  inet addr:172.23.4.2  Bcast:172.23.4.255  Mask:255.255.255.0
  ```

  Để xem default gateway trên Linux, bạn sử dụng lệnh `ip route`.

  ```bash
  $ ip route
  default via 172.23.4.254 dev eth0
  ```

- **Trên Cisco IOS**: Bạn sử dụng lệnh `show ip interface brief` để kiểm tra địa chỉ IP của các giao diện.

  Ví dụ:
  ```bash
  R1# show ip interface brief
  Interface              IP-Address      OK? Method Status                Protocol
  FastEthernet0/0        192.168.10.1    YES manual up                    up
  ```
  Để xem chi tiết hơn, bao gồm cả subnet mask, bạn sử dụng lệnh `show ip interface`.

  ```bash
  R1# show ip interface FastEthernet0/0
  FastEthernet0/0 is up, line protocol is up 
    Internet address is 192.168.10.1/24
  ```

#### 3. Địa Chỉ Tĩnh và Địa Chỉ Tự Động

- **Địa chỉ tĩnh**: Thường được cấu hình thủ công trên các thiết bị quan trọng như server, router, switch, và firewall. Điều này đảm bảo rằng địa chỉ IP của các thiết bị này không thay đổi, giúp quản lý và bảo mật mạng tốt hơn.

- **Địa chỉ tự động**: Thường được cấp phát tự động qua DHCP (Dynamic Host Configuration Protocol) cho các thiết bị như laptop và PC. Điều này giúp quản lý địa chỉ IP dễ dàng hơn trong môi trường lớn, nơi có hàng ngàn thiết bị cần kết nối mạng.

### Kết Luận

Hiểu về cách thức mà địa chỉ IPv4 được viết và sử dụng trên các thiết bị là rất quan trọng để quản lý và cấu hình mạng hiệu quả. Trong các bài học tiếp theo, bạn sẽ học cách quản lý và sử dụng các địa chỉ này trong các mạng phức tạp hơn.
