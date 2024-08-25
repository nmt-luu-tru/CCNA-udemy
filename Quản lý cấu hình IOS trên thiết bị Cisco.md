### Quản lý cấu hình IOS trên thiết bị Cisco

Trong bài học này, bạn sẽ học cách quản lý cấu hình IOS trên các thiết bị Cisco, bao gồm cấu hình đang chạy (running configuration) và cấu hình khởi động (startup configuration).

#### Cấu hình trên thiết bị Cisco

Các thiết bị Cisco duy trì hai cấu hình chính:

1. **Cấu hình đang chạy (Running Configuration)**: Đây là cấu hình đang hoạt động trên thiết bị. Bất kỳ thay đổi nào bạn thực hiện sẽ được áp dụng ngay lập tức vào cấu hình đang chạy này.

2. **Cấu hình khởi động (Startup Configuration)**: Đây là cấu hình được lưu trữ trong **NVRAM** (bộ nhớ không thay đổi), và nó sẽ được tải khi thiết bị khởi động lại. Thay đổi trong cấu hình đang chạy sẽ không được lưu vĩnh viễn cho đến khi bạn sao chép chúng vào cấu hình khởi động.

#### Các lệnh cơ bản

- **`config t`**: Vào chế độ cấu hình toàn cục (global configuration) để thực hiện các thay đổi cấu hình.
- **`hostname <name>`**: Thay đổi tên máy của thiết bị.
- **`show running-config`**: Hiển thị cấu hình đang chạy.
- **`show startup-config`**: Hiển thị cấu hình khởi động được lưu trong NVRAM.
- **`copy running-config startup-config`**: Lưu cấu hình đang chạy vào cấu hình khởi động, đảm bảo thay đổi sẽ được giữ lại sau khi khởi động lại.
- **`erase startup-config`** hoặc **`write erase`**: Xóa cấu hình khởi động khỏi NVRAM.
- **`copy startup-config running-config`**: Sao chép cấu hình khởi động vào cấu hình đang chạy, hiệu quả trong việc khôi phục cấu hình.

#### Ví dụ về quản lý cấu hình

1. **Thay đổi tên máy (hostname)**:
   - Đầu tiên, vào chế độ cấu hình toàn cục:
     ```bash
     Router# config t
     Router(config)#
     ```
   - Thay đổi tên máy thành `Router1`:
     ```bash
     Router(config)# hostname Router1
     Router1(config)#
     ```
   - Thay đổi này sẽ được phản ánh ngay lập tức trong cấu hình đang chạy.

2. **Xem cấu hình**:
   - Xem cấu hình đang chạy:
     ```bash
     Router1# show running-config
     ```
     **Kết quả**:
     ```bash
     hostname Router1
     !
     interface FastEthernet0/0
      ip address 192.168.1.1 255.255.255.0
     ...
     ```
   - Lưu ý rằng tên máy bây giờ là `Router1`.
   - Xem cấu hình khởi động:
     ```bash
     Router1# show startup-config
     ```
     **Kết quả**:
     ```bash
     hostname Router
     !
     interface FastEthernet0/0
      ip address 192.168.1.1 255.255.255.0
     ...
     ```
   - Tên máy trong cấu hình khởi động vẫn là `Router`, điều này cho thấy rằng các thay đổi chưa được lưu vào NVRAM.

3. **Lưu cấu hình đang chạy vào cấu hình khởi động**:
   - Lưu cấu hình đang chạy để nó được giữ lại sau khi khởi động lại:
     ```bash
     Router1# copy running-config startup-config
     Destination filename [startup-config]?
     Building configuration...
     [OK]
     ```
   - Bây giờ, nếu bạn chạy lại lệnh `show startup-config`, bạn sẽ thấy tên máy đã được cập nhật thành `Router1`.

#### Sao lưu và khôi phục cấu hình

1. **Sao lưu vào bộ nhớ flash**:
   - Sao lưu cấu hình đang chạy vào bộ nhớ flash:
     ```bash
     Router1# copy running-config flash:my-config
     Destination filename [my-config]?
     Building configuration...
     [OK]
     ```
   - Xác nhận sao lưu bằng cách liệt kê các tệp trong flash:
     ```bash
     Router1# show flash
     ```
     **Kết quả**:
     ```bash
     -rw-  4121  my-config
     ```

2. **Khôi phục từ flash**:
   - Để khôi phục cấu hình từ flash, đầu tiên xóa cấu hình khởi động:
     ```bash
     Router1# write erase
     Erasing the nvram filesystem will remove all files! Continue? [confirm]
     [OK]
     ```
   - Sau đó, sao chép cấu hình từ flash sang cấu hình khởi động và khởi động lại thiết bị:
     ```bash
     Router1# copy flash:my-config startup-config
     Destination filename [startup-config]?
     Building configuration...
     [OK]
     Router1# reload
     ```

3. **Sao lưu vào TFTP Server**:
   - Sao lưu cấu hình vào TFTP server:
     ```bash
     Router1# copy running-config tftp:
     Address or name of remote host []? 10.10.10.10
     Destination filename [router1-config]?
     Building configuration...
     [OK]
     ```

4. **Khôi phục từ TFTP Server**:
   - Khôi phục cấu hình từ TFTP server:
     ```bash
     Router1# copy tftp: startup-config
     Address or name of remote host []? 10.10.10.10
     Source filename []? router1-config
     Destination filename [startup-config]?
     Loading router1-config from 10.10.10.10: !!!!!!!
     [OK]
     ```

### Những nơi sao lưu và khôi phục cấu hình

1. **Flash Memory**:
   - **Ưu điểm**: Tiện lợi vì cấu hình được lưu trữ ngay trên thiết bị.
   - **Nhược điểm**: Nếu thiết bị gặp sự cố phần cứng nghiêm trọng, bạn có thể mất cả thiết bị lẫn bản sao lưu.

2. **TFTP Server**:
   - **Ưu điểm**: Lưu trữ bản sao lưu từ xa, giúp bảo vệ cấu hình khỏi các sự cố phần cứng của thiết bị.
   - **Nhược điểm**: Yêu cầu cấu hình kết nối mạng chính xác và hoạt động, và cần có TFTP server sẵn sàng.

3. **FTP Server**:
   - **Ưu điểm**: Tương tự như TFTP nhưng hỗ trợ nhiều tính năng bảo mật hơn như xác thực người dùng.
   - **Nhược điểm**: Cần cấu hình thêm trên thiết bị và FTP server để đảm bảo bảo mật.

4. **RCP (Remote Copy Protocol)**:
   - **Ưu điểm**: Tốc độ sao lưu nhanh và hỗ trợ xác thực.
   - **Nhược điểm**: Ít được sử dụng hơn và yêu cầu cấu hình đặc biệt.

5. **USB Flash Drive (với các thiết bị có cổng USB)**:
   - **Ưu điểm**: Dễ dàng sao lưu và khôi phục, không phụ thuộc vào kết nối mạng.
   - **Nhược điểm**: Phụ thuộc vào khả năng truy cập vật lý vào thiết bị.

### Những điểm cần nhớ

- **Cấu hình đang chạy vs. Cấu hình khởi động**: Các thay đổi bạn thực hiện sẽ ngay lập tức được áp dụng vào cấu hình đang chạy. Để đảm bảo chúng được giữ lại sau khi khởi động lại, bạn phải lưu chúng vào cấu hình khởi động.
- **Sao lưu và khôi phục**: Luôn sao lưu cấu hình của bạn thường xuyên và lưu trữ chúng ở nơi an toàn, chẳng hạn như trên TFTP server, đặc biệt là trước khi thực hiện những thay đổi lớn.
- **Hiểu về ngữ cảnh lệnh**: Đảm bảo bạn đang ở đúng chế độ (cấu hình toàn cục, chế độ EXEC ưu tiên, v.v.) khi nhập lệnh. Tiền tố `do` cho phép bạn chạy lệnh `show` từ chế độ cấu hình toàn cục mà không cần chuyển đổi ngữ cảnh.

Hiểu và quản lý các cấu hình này một cách hiệu quả là rất quan trọng để duy trì sự ổn định của mạng và đảm bảo rằng các thay đổi được áp dụng chính xác và bền vững.
