
### Bước 1: Vào chế độ cấu hình
Truy cập vào chế độ cấu hình trên router:
```plaintext
Router> enable
Router# configure terminal
```

### Bước 2: Cấu hình DHCP Pool
Tạo DHCP pool với tên và cấu hình các thông số cần thiết như địa chỉ mạng, dải địa chỉ cấp phát, địa chỉ gateway và DNS:

```plaintext
Router(config)# ip dhcp pool LAN
Router(dhcp-config)# network 192.168.10.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.10.1
Router(dhcp-config)# dns-server 8.8.8.8
Router(dhcp-config)# exit
```

### Bước 3: Cấu hình loại bỏ địa chỉ IP không cấp phát (nếu cần)
Nếu có một số địa chỉ IP muốn loại trừ khỏi dải cấp phát của DHCP (ví dụ các thiết bị tĩnh), cấu hình như sau:

```plaintext
Router(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.10
```
Lệnh này sẽ loại trừ các địa chỉ IP từ 192.168.10.1 đến 192.168.10.10 khỏi danh sách cấp phát.

### Bước 4: Kích hoạt cổng giao diện
Đảm bảo rằng cổng giao diện đã được cấu hình địa chỉ IP và kích hoạt để cấp phát IP cho các thiết bị trong mạng:

```plaintext
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip address 192.168.10.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
```

Thêm đổi tên và lưu cấu hình như cơ bản.
