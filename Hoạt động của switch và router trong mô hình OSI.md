Switch và router là hai thiết bị mạng quan trọng, hoạt động ở các tầng khác nhau trong mô hình OSI, và chúng có vai trò và chức năng riêng biệt trong việc xử lý và chuyển tiếp dữ liệu trong mạng.

### **Hoạt động của Switch trong mô hình OSI:**

- **Tầng Hoạt Động:** Switch hoạt động chủ yếu ở **Tầng 2: Data Link Layer (Lớp Liên Kết Dữ Liệu)**, nhưng một số switch thông minh có thể hoạt động đến **Tầng 3: Network Layer**.
  
- **Chức Năng Chính:**
  - **Chuyển tiếp frame:** Switch chuyển tiếp các frame dữ liệu giữa các thiết bị trong cùng một mạng LAN dựa trên địa chỉ MAC của thiết bị đích. Switch xây dựng và duy trì một bảng địa chỉ MAC (MAC Address Table) để ghi nhớ các địa chỉ MAC và cổng kết nối tương ứng, từ đó xác định cổng nào để chuyển tiếp frame.
  - **Giảm xung đột:** Switch chia nhỏ các miền xung đột (collision domains) bằng cách chỉ chuyển tiếp frame đến cổng đích thay vì phát tán đến tất cả các cổng, giúp tăng hiệu suất mạng.
  - **Học địa chỉ MAC:** Khi switch nhận được một frame, nó học địa chỉ MAC của thiết bị nguồn và cập nhật bảng địa chỉ MAC của nó.

- **Ví dụ Hoạt Động:**
  - Khi PC1 gửi dữ liệu đến PC2 qua switch, switch kiểm tra địa chỉ MAC đích trong frame và sử dụng bảng MAC của mình để quyết định chuyển frame đến cổng nào để frame đến được PC2 một cách chính xác và nhanh chóng.

### **Hoạt động của Router trong mô hình OSI:**

- **Tầng Hoạt Động:** Router hoạt động chủ yếu ở **Tầng 3: Network Layer (Lớp Mạng)**.

- **Chức Năng Chính:**
  - **Định tuyến gói tin:** Router định tuyến gói tin giữa các mạng khác nhau dựa trên địa chỉ IP. Nó sử dụng các bảng định tuyến (Routing Tables) để quyết định đường đi tốt nhất cho gói tin từ mạng nguồn đến mạng đích.
  - **Kết nối các mạng:** Router kết nối các mạng LAN khác nhau hoặc kết nối mạng LAN với mạng WAN (như Internet), cho phép các thiết bị ở các mạng khác nhau giao tiếp với nhau.
  - **Phân chia miền quảng bá:** Router chia nhỏ các miền quảng bá (broadcast domains), giúp ngăn chặn các gói tin quảng bá không cần thiết lan truyền qua các mạng khác nhau.
  - **Chuyển đổi giao thức:** Router có thể chuyển đổi dữ liệu giữa các giao thức mạng khác nhau (ví dụ từ IPv4 sang IPv6).

- **Ví dụ Hoạt Động:**
  - Khi PC0 ở mạng của Switch1 muốn gửi dữ liệu đến PC6 ở mạng của Switch3, router sẽ nhận gói tin từ Switch1, đọc địa chỉ IP đích trong gói tin, và dựa vào bảng định tuyến của nó, router quyết định chuyển gói tin sang mạng của Switch3 để đến được PC6.

### **Sự Khác Biệt Giữa Switch và Router trong Mô hình OSI:**
- **Switch** hoạt động ở Tầng 2, chuyển tiếp dữ liệu trong cùng một mạng LAN dựa trên địa chỉ MAC, và không tham gia định tuyến giữa các mạng khác nhau.
- **Router** hoạt động ở Tầng 3, định tuyến dữ liệu giữa các mạng khác nhau dựa trên địa chỉ IP, giúp các thiết bị trong các mạng khác nhau có thể giao tiếp với nhau.
