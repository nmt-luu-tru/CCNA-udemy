### Quy Trình Khởi Động Của Router Và Switch

Để hiểu được quy trình khởi động của router và switch, chúng ta cần tìm hiểu về các loại bộ nhớ có trên thiết bị. Có bốn loại bộ nhớ chính được tích hợp trên các thiết bị này:

1. **ROM (Read Only Memory):** Bộ nhớ chỉ đọc, được sử dụng khi thiết bị được bật nguồn.
2. **Flash:** Lưu trữ hệ điều hành IOS. Trên các thiết bị cũ, nó được gắn trên bo mạch chủ, trong khi trên các thiết bị mới hơn, nó có thể là thẻ CompactFlash có thể tháo rời.
3. **NVRAM (Non-Volatile RAM):** Lưu trữ cấu hình khởi động (startup-config).
4. **RAM (Random Access Memory):** Bộ nhớ làm việc chính của thiết bị, lưu trữ cấu hình đang chạy (running-config) và hình ảnh hệ điều hành IOS khi khởi động.

Ngoài ra, bạn cũng có thể sử dụng bộ nhớ ngoài như USB để hỗ trợ trong quá trình khôi phục hệ thống.

### Quy Trình Khởi Động

1. **ROM:** Khi thiết bị bật nguồn, ROM sẽ thực hiện Power On Self Test (POST) để kiểm tra phần cứng, sau đó tải bootstrap. Bootstrap tìm và tải hình ảnh IOS từ Flash.
   - Nếu không tìm thấy IOS trong Flash, thiết bị sẽ chuyển đến ROMMON prompt, cho biết rằng thiết bị không khởi động được. ROMMON có thể được sử dụng để khôi phục thiết bị bằng cách boot từ USB hoặc máy chủ TFTP bên ngoài.

2. **Flash:** ROM tìm kiếm hệ điều hành IOS trong Flash và tải hình ảnh đầu tiên tìm thấy. Bạn có thể thay đổi thứ tự này bằng lệnh `boot system flash [tên hình ảnh]` trong cấu hình global.
   - Khi thiết bị mới từ nhà máy, Flash thường chỉ có một bản IOS. Khi nâng cấp, bạn có thể tải phiên bản mới và lưu vào Flash, sau đó cấu hình thiết bị boot từ phiên bản mới này.

3. **NVRAM:** Sau khi tải IOS, thiết bị sẽ tải cấu hình khởi động từ NVRAM, và sao chép nó thành cấu hình đang chạy trong RAM. Nếu không tìm thấy cấu hình khởi động (do thiết bị mới hoặc vừa reset), thiết bị sẽ chạy Setup Wizard.
   - Để lưu cấu hình đang chạy thành cấu hình khởi động, sử dụng lệnh `copy running-config startup-config`.

4. **RAM:** Là nơi làm việc chính của thiết bị, lưu trữ cấu hình đang chạy và IOS sau khi tải từ Flash và NVRAM. RAM là bộ nhớ dễ bay hơi, sẽ mất dữ liệu khi thiết bị bị tắt nguồn hoặc khởi động lại.

### Các Lưu Ý Khác

- **VLAN Database:** Được lưu trữ trong file `vlan.dat`, nằm ở Flash hoặc NVRAM tùy thuộc vào model switch.
- **TFTP Server:** Hệ thống có thể tải hình ảnh hệ điều hành hoặc cấu hình từ máy chủ TFTP thay vì từ Flash hoặc NVRAM, nhưng điều này không được khuyến khích do rủi ro mất kết nối với TFTP server.

### Quy Trình Tổng Quan:

1. **ROM:** Thực hiện POST, tải bootstrap.
2. **Flash:** Bootstrap tìm và tải IOS từ Flash.
3. **NVRAM:** IOS tìm và tải cấu hình khởi động từ NVRAM.
4. **RAM:** Thiết bị sử dụng RAM cho hoạt động làm việc.

Việc nắm vững quy trình khởi động và các loại bộ nhớ trên router và switch sẽ giúp bạn quản lý và xử lý sự cố thiết bị hiệu quả hơn. Trong phần tiếp theo, chúng ta sẽ thực hành các bước này trong môi trường lab để hiểu rõ hơn về cách thức hoạt động thực tế của quy trình khởi động trên thiết bị mạng.
