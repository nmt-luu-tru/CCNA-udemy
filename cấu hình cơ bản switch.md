
### 1. Đặt tên cho Switch
```plaintext
Switch> enable
Switch# configure terminal
Switch(config)# hostname Switch1
```


### 2. Cấu hình địa chỉ IP cho Switch (quản lý từ xa)
Để quản lý switch từ xa qua Telnet hoặc SSH, bạn cần cấu hình địa chỉ IP trên VLAN 1 (hoặc VLAN quản lý):

```plaintext
Switch1(config)# interface vlan 1
Switch1(config-if)# ip address 192.168.1.2 255.255.255.0
Switch1(config-if)# no shutdown
Switch1(config-if)# exit
```

### 3. Thiết lập Default Gateway cho Switch
Để switch có thể kết nối ra ngoài mạng, bạn cần đặt Default Gateway:

```plaintext
Switch1(config)# ip default-gateway 192.168.1.1
```

### 4. Lưu cấu hình vào NVRAM
Để lưu cấu hình và đảm bảo rằng cấu hình không bị mất khi switch khởi động lại:

```plaintext
Switch1# write memory
```

Hoặc:

```plaintext
Switch1# copy running-config startup-config
```
