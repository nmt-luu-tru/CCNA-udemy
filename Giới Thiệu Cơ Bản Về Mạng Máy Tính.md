### Giới Thiệu Cơ Bản Về Mạng Máy Tính

Trong bài học này, chúng ta sẽ tìm hiểu những khái niệm cơ bản về mạng máy tính. Nếu bạn đã có kiến thức về switch, router, và cấu trúc mạng (network topology), bạn có thể bỏ qua bài học này. Nhưng nếu bạn mới bắt đầu, hãy cùng tôi khám phá một số khái niệm cơ bản về mạng.

### 1. **Mạng Cục Bộ (Local Area Network - LAN)**

Hãy tưởng tượng rằng công ty của chúng ta có một văn phòng ở New York. Trong văn phòng này, chúng ta có các thiết bị đầu cuối (end hosts) như máy tính cá nhân (PC), máy chủ (server), và máy in. Các thiết bị này cần kết nối và giao tiếp với nhau. Để thực hiện điều này, chúng ta sẽ sử dụng **switch**.

- **Switch:** Đây là một thiết bị mạng có nhiều cổng, cho phép kết nối nhiều thiết bị với nhau thông qua cáp Ethernet. Switch tạo ra một mạng cục bộ (LAN) trong văn phòng, cho phép các thiết bị giao tiếp với nhau. 
- **Wireless Access Point (WAP):** Nếu có laptop cần kết nối không dây, chúng ta sẽ sử dụng WAP, kết nối với switch để tạo ra mạng không dây (Wireless Network).

Như vậy, chúng ta đã thiết lập một **Local Area Network (LAN)** tại văn phòng New York. LAN là mạng kết nối các thiết bị trong cùng một khu vực địa lý nhỏ, như một văn phòng hoặc một khuôn viên trường đại học.

### 2. **Kết Nối Ra Ngoài Internet**

Các thiết bị trong văn phòng không chỉ cần giao tiếp với nhau mà còn cần kết nối ra ngoài Internet. Để thực hiện điều này, chúng ta cần sử dụng một thiết bị phức tạp hơn gọi là **router**.

- **Router:** Router chịu trách nhiệm đưa ra các quyết định định tuyến phức tạp để chuyển tiếp lưu lượng giữa các khu vực mạng khác nhau. Router kết nối mạng nội bộ của bạn với Internet và có thể hỗ trợ nhiều loại cổng kết nối khác nhau.

Ngoài ra, để bảo vệ mạng nội bộ khỏi các mối đe dọa từ Internet, chúng ta cần sử dụng **firewall**.

- **Firewall:** Đây là thiết bị bảo mật, giúp bảo vệ các phần khác nhau của mạng nội bộ khỏi các cuộc tấn công từ bên ngoài. Firewall có thể chặn hoặc cho phép lưu lượng mạng dựa trên các quy tắc bảo mật được thiết lập trước.

### 3. **Mạng Diện Rộng (Wide Area Network - WAN)**

Trong một công ty lớn, chúng ta có thể có nhiều văn phòng tại các địa điểm khác nhau. Ví dụ, ngoài văn phòng ở New York, công ty còn có một văn phòng ở Boston. Mỗi văn phòng sẽ có một **LAN** riêng và kết nối ra ngoài Internet.

Tuy nhiên, vì cả hai văn phòng đều thuộc cùng một công ty, chúng ta muốn các thiết bị ở cả New York và Boston có thể giao tiếp với nhau. Có hai cách để làm điều này:

- **Kết nối qua Internet:** Thiết lập một kết nối bảo mật qua Internet.
- **Kết nối chuyên dụng:** Sử dụng một kết nối chuyên dụng giữa hai router tại mỗi văn phòng để tạo thành **Wide Area Network (WAN)**, cho phép kết nối trực tiếp giữa các văn phòng.

### 4. **Các Đặc Điểm của Mạng**

Khi thiết kế và triển khai một mạng, chúng ta cần xem xét một số đặc điểm quan trọng:

- **Topology:** Cấu trúc liên kết mạng (topology) là cách các thiết bị được kết nối với nhau trong mạng.
- **Tốc độ mạng:** Tốc độ của mạng càng cao thì chi phí thường càng lớn. Chi phí này phụ thuộc vào loại thiết bị, kích thước của mạng và công nghệ được sử dụng.
- **Bảo mật:** Bên cạnh firewall, các thiết bị khác như router và switch cũng có thể có các tính năng bảo mật, cùng với các hệ thống bảo vệ khác như **Intrusion Prevention Systems (IPS)**.
- **Tính sẵn sàng (Availability):** Để đảm bảo rằng mạng luôn hoạt động, chúng ta cần thiết kế sao cho không có điểm hỏng duy nhất (single point of failure). Điều này thường được thực hiện bằng cách sử dụng các thành phần dự phòng.
- **Khả năng mở rộng (Scalability):** Mạng cần được thiết kế sao cho dễ dàng mở rộng khi công ty phát triển mà không cần phải thiết kế lại toàn bộ hệ thống.
- **Độ tin cậy (Reliability):** Mạng phải đáng tin cậy và có thể duy trì hoạt động liên tục mà không gặp sự cố.

### **Kết Luận**

Trên đây là một cái nhìn tổng quan nhanh về mạng máy tính. Mạng máy tính là một hệ thống cho phép các thiết bị kết nối và giao tiếp với nhau, cả trong cùng một khu vực và qua các khoảng cách địa lý rộng lớn. Hiểu rõ các thành phần và đặc điểm của mạng sẽ giúp bạn thiết kế và duy trì một hệ thống mạng hiệu quả và an toàn.
