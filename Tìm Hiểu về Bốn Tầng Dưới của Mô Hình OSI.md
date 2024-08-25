### Tìm Hiểu về Bốn Tầng Dưới của Mô Hình OSI

Trong bài học này, chúng ta sẽ tập trung vào bốn tầng dưới của mô hình OSI, đó là các tầng mà các kỹ sư mạng đặc biệt quan tâm. Đây là những phần quan trọng và cơ bản nhất trong mạng máy tính. Mỗi tầng trong số này sẽ có phần chuyên sâu riêng trong khóa học, nhưng trước tiên, chúng ta cần nắm vững các định nghĩa cần thiết cho kỳ thi.

### 1. **Tầng 4: Transport Layer (Lớp Vận Chuyển)**

- **Chức Năng:** Tầng Vận Chuyển định nghĩa các dịch vụ để phân đoạn, truyền tải và tái lập lại dữ liệu giữa các thiết bị đầu cuối. Nó chia các tập tin lớn thành các phân đoạn nhỏ hơn, giúp giảm thiểu các vấn đề trong quá trình truyền tải.

- **Đặc Điểm:** Tầng này sử dụng các giao thức như TCP (Transmission Control Protocol) hoặc UDP (User Datagram Protocol). Nếu muốn đảm bảo tính tin cậy trong giao tiếp giữa hai thiết bị, chúng ta sẽ sử dụng TCP. Nếu tốc độ quan trọng hơn tính tin cậy, chẳng hạn như trong truyền tải âm thanh hoặc video, chúng ta sẽ sử dụng UDP. Một yếu tố quan trọng khác của tầng này là số cổng (port number), ví dụ: cổng 80 cho HTTP (web), cổng 25 cho SMTP (email).

### 2. **Tầng 3: Network Layer (Lớp Mạng)**

- **Chức Năng:** Tầng Mạng cung cấp khả năng kết nối và lựa chọn đường dẫn giữa hai hệ thống máy chủ có thể ở trên các mạng khác nhau về mặt địa lý. Tầng này quản lý kết nối của các thiết bị bằng cách cung cấp địa chỉ logic, cụ thể là địa chỉ IP.

- **Đặc Điểm:** Thông tin quan trọng nhất tại tầng này là địa chỉ IP nguồn và đích. Các router là các thiết bị hoạt động ở tầng 3, chúng sử dụng thông tin này để định tuyến gói tin qua mạng.

### 3. **Tầng 2: Data Link Layer (Lớp Liên Kết Dữ Liệu)**

- **Chức Năng:** Tầng Liên Kết Dữ Liệu định nghĩa cách dữ liệu được định dạng để truyền tải và cách truy cập vào phương tiện vật lý được kiểm soát. Tầng này thường bao gồm các cơ chế phát hiện và sửa lỗi để đảm bảo việc truyền tải dữ liệu tin cậy.

- **Đặc Điểm:** Thông tin quan trọng ở đây là địa chỉ tầng 2 (địa chỉ MAC). Các công nghệ tầng 2 khác nhau sử dụng các định dạng địa chỉ khác nhau. Ví dụ, công nghệ Ethernet sử dụng địa chỉ MAC, trong khi các công nghệ cũ như Frame Relay sử dụng các số DLCI. Switch là các thiết bị hoạt động ở tầng 2, chúng nhận biết và xử lý thông tin tại tầng này.

### 4. **Tầng 1: Physical Layer (Lớp Vật Lý)**

- **Chức Năng:** Tầng Vật Lý liên quan đến các thành phần vật lý thực sự của mạng, như cáp kết nối và các tín hiệu điện.

- **Đặc Điểm:** Tầng này định nghĩa các thông số kỹ thuật cần thiết để kích hoạt, duy trì và hủy kích hoạt liên kết vật lý giữa các thiết bị đầu cuối. Ví dụ, các mức điện áp, tốc độ truyền dữ liệu vật lý, khoảng cách truyền dẫn tối đa, và các đầu nối vật lý.

### **Kết Luận**

Bốn tầng dưới của mô hình OSI là nền tảng cho việc thiết kế và quản lý mạng. Mỗi tầng có một vai trò quan trọng trong việc đảm bảo dữ liệu được truyền tải chính xác và hiệu quả từ thiết bị này sang thiết bị khác. Trong các phần tiếp theo của khóa học, chúng ta sẽ đi sâu hơn vào từng tầng này để hiểu rõ hơn về cách chúng hoạt động và tương tác với nhau.
