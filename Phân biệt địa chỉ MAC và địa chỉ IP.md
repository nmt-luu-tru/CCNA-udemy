Địa chỉ MAC và địa chỉ IP đều là các loại địa chỉ được sử dụng để nhận diện thiết bị trong mạng, nhưng chúng có những điểm khác biệt rõ ràng về mục đích, phạm vi sử dụng, và cách thức hoạt động:

### 1. **Địa chỉ MAC (Media Access Control)**
   - **Định nghĩa:** Địa chỉ MAC là một địa chỉ vật lý duy nhất được gán cho mỗi thiết bị mạng bởi nhà sản xuất. Địa chỉ này gồm 48 bit (6 byte) và thường được biểu diễn dưới dạng 12 ký tự thập lục phân (ví dụ: 00:1A:2B:3C:4D:5E).
   - **Phạm vi hoạt động:** Hoạt động ở tầng 2 (Data Link Layer) của mô hình OSI.
   - **Chức năng:** Định danh duy nhất các thiết bị trong cùng một mạng LAN (Local Area Network). Địa chỉ MAC giúp các thiết bị trong mạng cục bộ xác định và trao đổi dữ liệu trực tiếp với nhau.
   - **Tính chất:** Cố định và không thay đổi; nó được "đốt cháy" vào phần cứng của thiết bị mạng, như card mạng hoặc các thiết bị NIC (Network Interface Card).
   - **Ví dụ:** Khi một switch chuyển tiếp dữ liệu trong mạng LAN, nó sử dụng địa chỉ MAC để xác định cổng đích dựa trên địa chỉ MAC đích của frame.

### 2. **Địa chỉ IP (Internet Protocol)**
   - **Định nghĩa:** Địa chỉ IP là một địa chỉ logic được gán cho thiết bị trong mạng để định danh và định tuyến giữa các mạng khác nhau. Địa chỉ này có thể là IPv4 (32 bit, ví dụ: 192.168.1.1) hoặc IPv6 (128 bit, ví dụ: 2001:0db8:85a3:0000:0000:8a2e:0370:7334).
   - **Phạm vi hoạt động:** Hoạt động ở tầng 3 (Network Layer) của mô hình OSI.
   - **Chức năng:** Định danh các thiết bị trên các mạng khác nhau và giúp định tuyến các gói tin từ mạng này đến mạng khác. Địa chỉ IP có thể thay đổi tùy vào cấu hình mạng và thiết bị.
   - **Tính chất:** Có thể thay đổi, được quản lý bởi phần mềm (hệ điều hành hoặc DHCP server). Địa chỉ IP có thể được cấu hình tĩnh (do người quản trị mạng gán) hoặc động (được gán tự động bởi DHCP).
   - **Ví dụ:** Khi một gói tin được gửi từ một thiết bị ở mạng này đến một thiết bị ở mạng khác, router sử dụng địa chỉ IP để xác định đường đi và định tuyến gói tin đến đích.

### **Sự khác biệt chính:**
- **Địa chỉ MAC** là địa chỉ vật lý, cố định và dùng để nhận diện các thiết bị trong cùng một mạng cục bộ (LAN).
- **Địa chỉ IP** là địa chỉ logic, có thể thay đổi và dùng để định danh và định tuyến giữa các mạng khác nhau (LAN, WAN, Internet).

### **Ví dụ:**
- Khi bạn gửi dữ liệu từ máy tính của mình đến một máy chủ trên mạng internet, địa chỉ MAC sẽ được sử dụng trong phần mạng cục bộ để chuyển các frame từ máy tính đến router đầu tiên. Sau đó, địa chỉ IP được sử dụng để định tuyến các gói tin qua các router và mạng khác nhau đến đích cuối cùng.
