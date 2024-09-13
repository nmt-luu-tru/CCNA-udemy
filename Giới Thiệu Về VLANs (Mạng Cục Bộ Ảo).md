### Giới Thiệu Về VLANs (Mạng Cục Bộ Ảo)

Trong bài giảng này, chúng ta sẽ tìm hiểu về VLANs (Mạng Cục Bộ Ảo), một tính năng lớp 2 được triển khai trên các switch. Để hiểu tại sao VLANs quan trọng, chúng ta cần hiểu vấn đề mà chúng giải quyết. Trước tiên, hãy xem qua hoạt động của các router và switch.

### Hoạt Động Của Router

Routers hoạt động ở lớp 3 trong mô hình OSI, có nhiệm vụ chính là định tuyến lưu lượng giữa các subnet IP khác nhau. Ví dụ, nếu các máy tính trong phòng kỹ thuật nằm trong subnet 10.10.10.0/24 và các máy tính phòng kế toán nằm trong subnet 10.10.20.0/24, router có thể sử dụng các quy tắc bảo mật để chặn lưu lượng giữa các subnet này. Router cũng không chuyển tiếp lưu lượng broadcast, giúp tăng cường hiệu suất và bảo mật bằng cách chia mạng thành các miền nhỏ hơn ở lớp 3.

### Hoạt Động Của Switch

Switches hoạt động ở lớp 2 của mô hình OSI và mặc định chuyển tiếp lưu lượng broadcast. Điều này làm cho một mạng switch trong khuôn viên trở thành một miền broadcast lớn, gây ra vấn đề về hiệu suất và bảo mật. Khi có lưu lượng unicast trong cùng subnet, switch sẽ chuyển lưu lượng đến đúng địa chỉ MAC đã học được, giúp cải thiện hiệu suất và bảo mật. Tuy nhiên, với lưu lượng broadcast, switch sẽ gửi đến tất cả các cổng, bao gồm cả các subnet IP khác nhau.

### Vấn Đề Với Lưu Lượng Broadcast

Lưu lượng broadcast có thể làm giảm bảo mật vì nó bỏ qua các quy tắc bảo mật lớp 3 trên router hoặc firewall. Ngoài ra, nó còn ảnh hưởng đến hiệu suất khi tất cả các thiết bị cuối phải xử lý lưu lượng không cần thiết, gây lãng phí băng thông trên các liên kết mạng. Ví dụ, nếu PC của phòng Sales gửi lưu lượng broadcast, nó sẽ được switch chuyển tiếp đến tất cả các thiết bị, bao gồm cả các PC phòng kỹ thuật và kế toán, mặc dù không cần thiết.

### VLANs Là Giải Pháp

VLANs giúp cải thiện hiệu suất và bảo mật bằng cách chia mạng thành các miền broadcast riêng biệt ở lớp 2 trên các switch. Thông thường, có sự tương quan 1-1 giữa một subnet IP và một VLAN. Ví dụ, ta có thể tạo VLAN kỹ thuật và VLAN sales trên switch, sau đó đưa các PC và giao diện router tương ứng vào các VLAN này. Switch chỉ cho phép lưu lượng trong cùng một VLAN, do đó, lưu lượng broadcast chỉ được gửi đến các cổng thuộc VLAN tương ứng, giúp cải thiện cả bảo mật lẫn hiệu suất.

### Lợi Ích Của VLANs

Với VLANs, lưu lượng unicast vẫn được chuyển đúng như trước, nhưng lưu lượng broadcast sẽ chỉ giới hạn trong phạm vi của VLAN. Điều này có nghĩa là nếu PC phòng Sales gửi lưu lượng broadcast, chỉ các thiết bị trong VLAN Sales mới nhận được, còn các thiết bị trong VLAN kỹ thuật sẽ không bị ảnh hưởng. VLANs giúp tối ưu hóa mạng, tăng cường bảo mật và đảm bảo lưu lượng chỉ đến những nơi cần thiết.
