### Giải Thích Chi Tiết Về Tầng 3 của Mô Hình OSI: Tầng Mạng (Network Layer)

Trong bài học này, chúng ta sẽ tìm hiểu về Tầng 3 của mô hình OSI, đó là Tầng Mạng (Network Layer). Tầng Mạng chịu trách nhiệm định tuyến các gói tin (packets) đến đích của chúng trong mạng, do đó, các bộ định tuyến (routers) hoạt động ở Tầng Mạng. Ngoài ra, Tầng Mạng còn chịu trách nhiệm về Chất Lượng Dịch Vụ (Quality of Service - QoS).

#### Chất Lượng Dịch Vụ (Quality of Service - QoS)
QoS là cơ chế giúp ưu tiên một loại lưu lượng nhất định để đảm bảo chất lượng dịch vụ tốt hơn cho nó so với các loại lưu lượng khác. Ví dụ, nếu bạn đang chạy thoại hoặc video qua IP, loại dữ liệu này rất nhạy cảm với độ trễ. Do đó, chúng ta sẽ ưu tiên cho nó một chất lượng dịch vụ tốt hơn so với lưu lượng như email, vốn không quá nhạy cảm với độ trễ.

#### Giao Thức IP
Giao thức phổ biến nhất ở Tầng 3 là Giao thức Internet (Internet Protocol - IP). Phiên bản hiện tại của IP là IPv4, và phần lớn bài học này tập trung vào IPv4. Ngoài ra, còn có IPv6, là phiên bản nâng cấp của IPv4. Trong các bài học sau, chúng ta sẽ tìm hiểu lý do tại sao chúng ta cần IPv6, cách sử dụng nó ngày nay và cách cấu hình nó.

IP là một giao thức không kết nối (connectionless protocol), nghĩa là không có sự xác nhận tại Tầng 3. Tuy nhiên, bạn vẫn có thể đảm bảo lưu lượng tin cậy bằng cách sử dụng TCP ở Tầng 4 hoặc các cơ chế khác ở các tầng cao hơn.

#### Các Giao Thức Khác ở Tầng 3
Ngoài IP, còn có các giao thức khác như ICMP (Internet Control Message Protocol), được sử dụng cho các công cụ như ping để kiểm tra kết nối mạng và IPSec (IP Security) để truyền tải dữ liệu mã hóa an toàn.

#### Địa Chỉ IP và Phân Chia Mạng
Địa chỉ IP là một cơ chế định địa chỉ logic được thực hiện ở Tầng 3. Người thiết kế mạng sử dụng địa chỉ IP để chia mạng tổng thể thành các mạng con nhỏ hơn, gọi là các subnet. Việc chia thành các subnet giúp cải thiện hiệu suất, bảo mật và làm cho việc khắc phục sự cố trở nên dễ dàng hơn. 

- **Cải thiện hiệu suất**: Thay vì có một mạng lớn, chúng ta chia nó thành các mạng con nhỏ hơn, giúp lưu lượng được giữ lại trong mạng con của nó thay vì lan rộng ra toàn bộ mạng.
  
- **Cải thiện bảo mật**: Ví dụ, nếu chúng ta có các máy chủ kế toán, chúng ta có thể đặt chúng trên một subnet riêng, và điều này giúp dễ dàng kiểm soát ai có quyền truy cập vào các máy chủ đó.

- **Dễ dàng khắc phục sự cố**: Khi mạng được chia thành các phần nhỏ hơn, nếu xảy ra sự cố, chúng ta dễ dàng xác định phần nào của mạng đang gặp vấn đề và tập trung vào đó.

#### Địa Chỉ IP vs. Địa Chỉ MAC
Ở Tầng 3, chúng ta sử dụng địa chỉ IP. Ở Tầng 2 (Data Link Layer), chúng ta sử dụng địa chỉ MAC, nếu sử dụng Ethernet. Địa chỉ IP là một cơ chế định địa chỉ logic, còn địa chỉ MAC là một cơ chế định địa chỉ phẳng toàn cầu.

### Cấu Trúc Header của Gói IP
Cấu trúc của một gói IP gồm nhiều trường quan trọng, như sau:

1. **Phiên bản** (Version): Là trường 4-bit xác định phiên bản của IP (IPv4 hoặc IPv6).
2. **Độ dài tiêu đề** (Header Length): Là trường 4-bit chỉ độ dài của phần tiêu đề IP.
3. **Loại dịch vụ** (Type of Service - ToS): Là byte sử dụng cho thông tin QoS, giúp đánh dấu loại lưu lượng và ưu tiên xử lý.
4. **Tổng độ dài** (Total Length): Là trường 16-bit chỉ tổng độ dài của gói tin IP.
5. **Thông tin phân mảnh** (Fragment Information): Dùng để giữ theo dõi các mảnh gói tin khi gói tin lớn hơn kích thước tối đa (MTU) phải được chia nhỏ.
6. **Thời gian sống (Time to Live - TTL)**: Là trường 8-bit, mỗi lần gói tin đi qua một router, TTL sẽ giảm đi 1. Nếu TTL bằng 0, router sẽ hủy gói tin, ngăn ngừa việc lặp lại vô hạn trong mạng.
7. **Giao thức (Protocol)**: Trường 8-bit chỉ loại giao thức ở Tầng 4, thường là TCP hoặc UDP.
8. **Tổng kiểm tra (Checksum)**: Dùng để kiểm tra gói tin có bị hỏng trong quá trình truyền tải hay không.
9. **Địa chỉ nguồn (Source IP Address)**: Địa chỉ IP của thiết bị gửi.
10. **Địa chỉ đích (Destination IP Address)**: Địa chỉ IP của thiết bị nhận.
11. **Tùy chọn tiêu đề (Header Options)**: Trường này cho phép thêm thông tin tùy chọn, nhưng không phổ biến.
12. **Dữ liệu (Data)**: Phần dữ liệu của gói tin.

### Kết Luận
Tầng Mạng (Layer 3) là một trong những tầng quan trọng nhất trong mô hình OSI, với nhiệm vụ định tuyến các gói tin đến đích của chúng và quản lý chất lượng dịch vụ (QoS). Giao thức IP là nền tảng cho việc truyền tải dữ liệu qua mạng, và cấu trúc của một gói IP chứa nhiều trường quan trọng giúp định nghĩa và xử lý gói tin trong mạng.
