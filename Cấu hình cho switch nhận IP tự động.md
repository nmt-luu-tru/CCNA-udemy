Trước khi cấu hình cho switch phải đảm bảo router đã cấu hình xong dhcp.
### Các bước cấu hình switch để nhận IP tự động từ DHCP:

### 1. Vào chế độ cấu hình của switch
Truy cập vào switch và chuyển sang chế độ cấu hình:
```plaintext
Switch> enable
Switch# configure terminal
```

### 2. Cấu hình giao diện VLAN để nhận IP từ DHCP
Giao diện VLAN (thường là VLAN 1 nếu không có VLAN quản lý khác) sẽ được cấu hình để nhận IP từ máy chủ DHCP.

```plaintext
Switch(config)# interface vlan 1
Switch(config-if)# ip address dhcp
Switch(config-if)# no shutdown
Switch(config-if)# exit
```

### 3. Cấu hình Default Gateway
Nếu switch cần kết nối ra ngoài mạng hoặc để quản lý từ xa, bạn cần cấu hình Default Gateway:

```plaintext
Switch(config)# ip default-gateway <Địa_chỉ_IP_gateway>
```

### 5. Lưu cấu hình
Để đảm bảo cấu hình được lưu lại và không mất khi khởi động lại switch:

```plaintext
Switch# write memory
```

Hoặc:

```plaintext
Switch# copy running-config startup-config
```
