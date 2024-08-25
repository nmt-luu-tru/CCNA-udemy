### Giới Thiệu về Mô Hình OSI

Trong bài học này, chúng ta sẽ tìm hiểu về mô hình OSI (Open Systems Interconnection). Đây là một tiêu chuẩn quốc tế do Tổ chức Tiêu chuẩn hóa Quốc tế (ISO) phát triển. Mô hình OSI không phải là một giao thức hay công nghệ thực tế, mà là một khung khái niệm, giúp tiêu chuẩn hóa cách các máy tính giao tiếp với nhau qua mạng.

### 1. **Cấu Trúc Bảy Tầng của Mô Hình OSI**

Mô hình OSI chia quá trình truyền dữ liệu thành bảy tầng (layers). Mỗi tầng thực hiện các nhiệm vụ cụ thể và cung cấp dịch vụ cho tầng liền kề.

- **Tầng 7: Application Layer (Lớp Ứng Dụng):** Tầng này cung cấp các dịch vụ mạng trực tiếp cho ứng dụng của người dùng, chẳng hạn như email, web, hoặc truyền file.
  
- **Tầng 6: Presentation Layer (Lớp Trình Bày):** Tầng này chịu trách nhiệm định dạng dữ liệu, mã hóa và giải mã dữ liệu để tầng ứng dụng có thể hiểu được.

- **Tầng 5: Session Layer (Lớp Phiên):** Tầng này quản lý các phiên giao tiếp (sessions) giữa các ứng dụng. Nó thiết lập, quản lý, và kết thúc các phiên giao tiếp.

- **Tầng 4: Transport Layer (Lớp Vận Chuyển):** Tầng này đảm bảo việc truyền dữ liệu giữa các máy chủ được thực hiện một cách đáng tin cậy hoặc nhanh chóng, tùy thuộc vào giao thức được sử dụng (TCP hoặc UDP).

- **Tầng 3: Network Layer (Lớp Mạng):** Tầng này định tuyến các gói dữ liệu qua mạng, đảm bảo rằng dữ liệu đến đúng đích thông qua các địa chỉ IP.

- **Tầng 2: Data Link Layer (Lớp Liên Kết Dữ Liệu):** Tầng này chịu trách nhiệm truyền dữ liệu giữa hai thiết bị trên cùng một mạng vật lý. Nó xử lý địa chỉ MAC và đảm bảo dữ liệu không bị lỗi khi truyền qua liên kết vật lý.

- **Tầng 1: Physical Layer (Lớp Vật Lý):** Tầng này chịu trách nhiệm về các kết nối vật lý giữa các thiết bị, như cáp, đầu nối, và tín hiệu điện.

### 2. **Quá Trình Đóng Gói và Giải Mã Dữ Liệu (Encapsulation and De-encapsulation)**

Khi một máy gửi dữ liệu, dữ liệu sẽ được "đóng gói" qua từng tầng của mô hình OSI, từ tầng Application xuống tầng Physical:

- **Bắt đầu từ Tầng 7:** Dữ liệu từ ứng dụng (ví dụ: email) được tạo ra ở tầng Application và được truyền xuống các tầng thấp hơn. 
- **Tầng 6, 5:** Dữ liệu được định dạng và quản lý phiên giao tiếp.
- **Tầng 4:** Dữ liệu được thêm thông tin về giao thức vận chuyển (như TCP/UDP) và số cổng để đảm bảo nó đến đúng ứng dụng trên máy nhận.
- **Tầng 3:** Địa chỉ IP của nguồn và đích được thêm vào để đảm bảo dữ liệu đến đúng máy nhận trên mạng.
- **Tầng 2:** Địa chỉ MAC được thêm vào để định tuyến dữ liệu qua mạng cục bộ.
- **Tầng 1:** Dữ liệu cuối cùng được chuyển thành tín hiệu điện và truyền qua dây cáp hoặc sóng không dây.

Khi dữ liệu đến máy nhận, quá trình này diễn ra ngược lại, được gọi là **de-encapsulation**. Máy nhận sẽ xử lý dữ liệu từ tầng Physical lên tầng Application, kiểm tra từng phần của gói dữ liệu để đảm bảo nó được gửi đến đúng ứng dụng.

### 3. **Lợi Ích của Mô Hình OSI**

Mô hình OSI mang lại nhiều lợi ích:

- **Tiêu chuẩn hóa:** Mô hình này giúp tiêu chuẩn hóa cách mà các thiết bị mạng giao tiếp với nhau, bất kể nhà sản xuất nào. Điều này giúp các thiết bị từ các nhà sản xuất khác nhau có thể hoạt động cùng nhau.
  
- **Tối ưu hóa chuyên môn:** Các kỹ sư mạng có thể tập trung vào một tầng cụ thể trong khi các nhà phát triển ứng dụng có thể tập trung vào các tầng cao hơn, chẳng hạn như tầng Application, Presentation, và Session.

- **Dễ dàng khắc phục sự cố:** Khi gặp sự cố mạng, bạn có thể phân tích vấn đề theo từng tầng, giúp quá trình khắc phục sự cố trở nên logic và có hệ thống hơn.

### 4. **Cách Nhớ Các Tầng của Mô Hình OSI**

Để dễ dàng nhớ tên và thứ tự của các tầng trong mô hình OSI, có nhiều câu viết tắt được sử dụng:

- **"Please Do Not Throw Sausage Pizza Away":** Đây là câu kinh điển giúp ghi nhớ các tầng từ thấp đến cao: Physical, Data Link, Network, Transport, Session, Presentation, Application.

### **Kết Luận**

Mô hình OSI là một công cụ vô cùng quan trọng trong việc hiểu và thiết kế mạng máy tính. Nó giúp tiêu chuẩn hóa và đơn giản hóa quá trình giao tiếp giữa các thiết bị, đồng thời cung cấp một phương pháp logic để phân tích và khắc phục sự cố mạng. Việc hiểu rõ mô hình này sẽ giúp bạn trở thành một kỹ sư mạng hiệu quả hơn.
