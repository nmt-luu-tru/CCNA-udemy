
### 1. Đặt tên cho Router
```plaintext
Router> enable
Router# configure terminal
Router(config)# hostname Router1
```

### 2. Cấu hình địa chỉ IP cho các cổng
Ví dụ: cấu hình địa chỉ IP cho cổng GigabitEthernet0/0:
```plaintext
Router1(config)# interface GigabitEthernet0/0
Router1(config-if)# ip address 192.168.1.1 255.255.255.0
Router1(config-if)# no shutdown
Router1(config-if)# exit
```

### 3. Lưu cấu hình
Để lưu cấu hình vào bộ nhớ NVRAM:
```plaintext
Router1# write memory
```
Hoặc:
```plaintext
Router1# copy running-config startup-config
```
