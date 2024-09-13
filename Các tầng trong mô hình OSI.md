

### 1. **Tầng 1: Physical Layer (Lớp Vật Lý)**
   - **Chức năng:** Tầng này chịu trách nhiệm truyền tín hiệu điện qua các cáp kết nối vật lý giữa các thiết bị như máy tính, switch, và router.
   - **Ví dụ:** Các kết nối cáp Ethernet giữa PC, switch, và router đều thuộc tầng vật lý. Tín hiệu điện từ PC0 được truyền qua cáp đến Switch1, sau đó từ Switch1 đến Router1.

### 2. **Tầng 2: Data Link Layer (Lớp Liên Kết Dữ Liệu)**
   - **Chức năng:** Tầng liên kết dữ liệu chịu trách nhiệm về việc truyền dữ liệu trong cùng một mạng cục bộ (LAN) thông qua địa chỉ MAC, và kiểm tra lỗi trong các frame dữ liệu.
   - **Ví dụ:** Khi PC0 gửi dữ liệu đến Server3 qua Switch1, Switch1 sử dụng địa chỉ MAC để định tuyến các frame đến Server3, đảm bảo rằng frame đến đúng đích trong cùng mạng LAN.

### 3. **Tầng 3: Network Layer (Lớp Mạng)**
   - **Chức năng:** Tầng mạng định tuyến các gói dữ liệu qua các mạng khác nhau bằng cách sử dụng địa chỉ IP, đảm bảo rằng gói dữ liệu đến đúng đích.
   - **Ví dụ:** Khi PC0 ở mạng của Switch1 muốn gửi dữ liệu đến PC6 ở mạng của Switch3, Router1 sẽ sử dụng địa chỉ IP để định tuyến gói dữ liệu từ mạng của Switch1 qua mạng của Switch3, đảm bảo gói tin đến được PC6.

### 4. **Tầng 4: Transport Layer (Lớp Vận Chuyển)**
   - **Chức năng:** Tầng vận chuyển đảm bảo việc truyền dữ liệu được thực hiện một cách đáng tin cậy thông qua TCP hoặc nhanh chóng qua UDP.
   - **Ví dụ:** Nếu PC0 gửi một file lớn đến Server3, tầng vận chuyển sẽ chia file thành nhiều segment nhỏ và sử dụng TCP để đảm bảo các segment đến đích đầy đủ và theo đúng thứ tự.

### 5. **Tầng 5: Session Layer (Lớp Phiên)**
   - **Chức năng:** Quản lý các phiên làm việc giữa các ứng dụng trên các thiết bị khác nhau, thiết lập và duy trì phiên giao tiếp.
   - **Ví dụ:** Khi PC1 thiết lập một phiên làm việc từ xa với Server0 để chạy một dịch vụ, tầng phiên đảm bảo rằng phiên làm việc này được duy trì cho đến khi hoàn tất.

### 6. **Tầng 6: Presentation Layer (Lớp Trình Bày)**
   - **Chức năng:** Chịu trách nhiệm mã hóa, giải mã và nén dữ liệu để đảm bảo dữ liệu có thể được hiểu giữa các thiết bị.
   - **Ví dụ:** Nếu PC3 gửi dữ liệu mã hóa đến Server0, tầng trình bày sẽ mã hóa dữ liệu trước khi gửi đi và Server0 sẽ giải mã dữ liệu sau khi nhận được.

### 7. **Tầng 7: Application Layer (Lớp Ứng Dụng)**
   - **Chức năng:** Tầng ứng dụng cung cấp các giao thức và dịch vụ cho các ứng dụng của người dùng, như HTTP, FTP, SMTP.
   - **Ví dụ:** Khi PC4 truy cập một trang web từ Server1, tầng ứng dụng sẽ sử dụng giao thức HTTP để yêu cầu và nhận dữ liệu trang web từ Server1, sau đó hiển thị trang web trên trình duyệt của PC4.

Quy trình này giúp đảm bảo rằng mỗi tầng thực hiện đúng chức năng của mình trong việc truyền tải dữ liệu qua mạng, từ tín hiệu vật lý đến các ứng dụng cuối cùng trên các thiết bị khác nhau trong sơ đồ mạng.
