### Giải Thích Chi Tiết Về Tầng 4 của Mô Hình OSI: Tầng Vận Chuyển (Transport Layer)

Trong bài học này, bạn sẽ học về Tầng 4 của mô hình OSI, đó là Tầng Vận Chuyển (Transport Layer). Tầng này chịu trách nhiệm cung cấp truyền tải dữ liệu giữa các thiết bị và đảm bảo các cơ chế phục hồi lỗi và kiểm soát luồng dữ liệu từ đầu đến cuối. Tuy nhiên, không phải giao thức nào ở Tầng 4 cũng hỗ trợ phục hồi lỗi và kiểm soát luồng dữ liệu, và điều này sẽ có những ảnh hưởng nhất định.

#### Kiểm Soát Luồng Dữ Liệu (Flow Control)
Kiểm soát luồng là quá trình điều chỉnh tốc độ truyền tải dữ liệu từ phía gửi để đảm bảo phía nhận có thể xử lý được lượng dữ liệu đó. Nếu bên gửi gửi dữ liệu quá nhanh, phía nhận có thể không kịp xử lý, đặc biệt khi tốc độ mạng của bên gửi nhanh hơn bên nhận. Khi đó, nếu kiểm soát luồng được bật, phía nhận sẽ có cơ chế để báo hiệu cho bên gửi giảm tốc độ truyền tải.

#### Phân Luồng Phiên Giao Tiếp (Session Multiplexing)
Một chức năng khác của Tầng 4 là phân luồng phiên giao tiếp. Điều này cho phép một thiết bị hỗ trợ nhiều phiên giao tiếp cùng lúc và quản lý các luồng dữ liệu riêng biệt qua cùng một liên kết.

#### Ví Dụ Cụ Thể
Giả sử chúng ta có một máy gửi bên trái và một số máy nhận bên phải. Máy gửi gửi một số dữ liệu email qua giao thức SMTP tới máy nhận đầu tiên qua cổng 25, và cũng gửi một số dữ liệu web qua giao thức HTTP tới máy nhận thứ hai qua cổng 80. Đồng thời, máy gửi cũng gửi dữ liệu email qua cổng 25 tới máy nhận thứ hai. 

Trong ví dụ này, máy gửi có ba phiên giao tiếp: một phiên tới máy nhận đầu tiên và hai phiên tới máy nhận thứ hai. Tầng Vận Chuyển (Transport Layer) có nhiệm vụ theo dõi và quản lý các phiên giao tiếp này bằng cách sử dụng các số cổng (port numbers).

#### Số Cổng (Port Numbers)
Mỗi luồng dữ liệu được gán một số cổng đích để xác định ứng dụng nào trên thiết bị nhận cần xử lý dữ liệu đó. Ví dụ, giao thức HTTP sử dụng cổng 80, còn giao thức SMTP sử dụng cổng 25. 

Máy gửi cũng thêm số cổng nguồn vào tiêu đề của Tầng 4. Tổ hợp của số cổng nguồn và số cổng đích giúp theo dõi các phiên giao tiếp.

#### Tường Lửa Trạng Thái (Stateful Firewalls)
Một cách sử dụng khác của số cổng là giúp các tường lửa trạng thái (stateful firewalls) theo dõi các kết nối. Ví dụ, nếu tường lửa cho phép lưu lượng truy cập ra ngoài từ máy gửi tới mạng bên phải, nó sẽ chỉ cho phép lưu lượng trở về nếu đó là lưu lượng trả lời từ kết nối đã được khởi tạo bởi máy gửi.

#### Giao Thức TCP và UDP
Hai giao thức phổ biến nhất ở Tầng 4 là TCP (Transmission Control Protocol) và UDP (User Datagram Protocol). TCP là một giao thức hướng kết nối, đảm bảo rằng dữ liệu được truyền tải theo thứ tự và không bị thiếu. Nó cũng hỗ trợ kiểm soát luồng và phục hồi lỗi.

UDP là một giao thức không hướng kết nối, tức là nó không đảm bảo dữ liệu sẽ đến nơi nhận hoặc đến theo đúng thứ tự. UDP không có kiểm soát luồng và phục hồi lỗi, nên nó thích hợp cho các ứng dụng yêu cầu tốc độ và thời gian thực như thoại và video.

#### Header của TCP và UDP
- **TCP Header**: Bao gồm các trường như số cổng nguồn, số cổng đích, số thứ tự (sequence number), số nhận dạng (acknowledgment number), độ dài tiêu đề, các bit điều khiển, cửa sổ (window), tổng kiểm tra (checksum), và các tùy chọn khác.
  
- **UDP Header**: Chỉ bao gồm các trường cơ bản như số cổng nguồn, số cổng đích, độ dài và tổng kiểm tra.

#### Ứng Dụng của TCP và UDP
Nhà phát triển ứng dụng có thể lựa chọn sử dụng TCP hay UDP tùy thuộc vào yêu cầu của ứng dụng. TCP thường được sử dụng cho các ứng dụng yêu cầu độ tin cậy cao, trong khi UDP được sử dụng cho các ứng dụng thời gian thực yêu cầu tốc độ và ít độ trễ.

#### Các Số Cổng Thông Dụng
- **TCP**: 
  - FTP (File Transfer Protocol): Cổng 21
  - SSH (Secure Shell): Cổng 22
  - Telnet: Cổng 23
  - HTTP (Web traffic): Cổng 80
  - HTTPS (Encrypted web traffic): Cổng 443
  
- **UDP**:
  - TFTP (Trivial File Transfer Protocol): Cổng 69
  - SNMP (Simple Network Management Protocol): Cổng 161
  
- **TCP và UDP**:
  - DNS (Domain Name System): Cổng 53

### Kết Luận
Tầng 4 của mô hình OSI rất quan trọng trong việc đảm bảo truyền tải dữ liệu đáng tin cậy giữa các thiết bị, với hai giao thức chính là TCP và UDP. Mỗi giao thức có những ưu và nhược điểm riêng, phù hợp với các loại ứng dụng khác nhau trong mạng.
