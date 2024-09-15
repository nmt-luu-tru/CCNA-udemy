**Telnet** và **SSH** là hai giao thức mạng phổ biến được sử dụng để kết nối và quản lý các thiết bị từ xa, chẳng hạn như máy chủ, bộ định tuyến, hoặc thiết bị mạng khác.

### Telnet
- **Telnet (Teletype Network)** là một giao thức mạng cũ cho phép kết nối từ xa với một thiết bị mạng qua giao diện dòng lệnh.
- **Chức năng chính:** Cung cấp một phiên làm việc từ xa, cho phép người dùng điều khiển thiết bị bằng các lệnh từ xa.
- **Bảo mật:** Telnet truyền dữ liệu dưới dạng văn bản rõ ràng, bao gồm cả thông tin đăng nhập (username, password), điều này khiến nó dễ bị tấn công bởi kẻ xấu (man-in-the-middle).
- **Sử dụng:** Phù hợp cho các môi trường không yêu cầu bảo mật cao hoặc các mạng nội bộ bảo mật.

### SSH
- **SSH (Secure Shell)** là một giao thức mạng bảo mật hơn, được phát triển để thay thế Telnet và cung cấp khả năng quản lý từ xa an toàn hơn.
- **Chức năng chính:** Giống như Telnet, SSH cung cấp một phiên làm việc từ xa, nhưng nó mã hóa toàn bộ dữ liệu truyền đi, bao gồm thông tin đăng nhập và lệnh điều khiển.
- **Bảo mật:** SSH sử dụng mã hóa để bảo vệ dữ liệu và thông tin đăng nhập, giúp ngăn chặn các cuộc tấn công như nghe lén và giả mạo.
- **Sử dụng:** Được sử dụng rộng rãi trong các môi trường yêu cầu tính bảo mật cao như quản trị hệ thống, quản lý máy chủ, và các dịch vụ đòi hỏi kết nối từ xa an toàn.

Tóm lại, Telnet là giao thức cũ với bảo mật kém, còn SSH là lựa chọn hiện đại và bảo mật hơn, thường được khuyên dùng cho các kết nối từ xa.
