### Hoạt Động Cơ Bản Của Router Và So Sánh Với Switch

Trong bài giảng này, chúng ta sẽ tìm hiểu về **router** – thiết bị hoạt động tại Tầng 3 (Layer 3) của mô hình OSI và cách nó so sánh với **switch** – thiết bị hoạt động tại Tầng 2 (Layer 2).

#### 1. **Chức Năng Của Router**
- **Router** thực hiện chức năng chính là **định tuyến** (routing) – định hướng lưu lượng giữa các **mạng con IP** (IP subnets) khác nhau. Nếu bạn muốn lưu lượng truyền từ một mạng con này đến mạng con khác, bạn sẽ cần đến một router.
- **IP (Internet Protocol)**, nằm ở Tầng 3 của mô hình OSI, là giao thức được router sử dụng để định tuyến lưu lượng. Điều này làm cho router trở thành một thiết bị Tầng 3. Router cũng có các giao diện vật lý (Layer 1) và cần hiểu địa chỉ MAC (Layer 2) để thực hiện chức năng của mình.

#### 2. **So Sánh Giữa Router Và Switch**
- **Router** là thiết bị Tầng 3, có khả năng định tuyến lưu lượng giữa các mạng con khác nhau. Nó hỗ trợ nhiều loại giao diện như Ethernet, Serial, ISDN, ADSL, trong khi **switch** chủ yếu chỉ hỗ trợ giao diện Ethernet.
- **Switch** là thiết bị Tầng 2, chỉ có thể chuyển lưu lượng giữa các host trong cùng một mạng LAN, không thể định tuyến giữa các mạng con khác nhau như router.
- **Switches** thường có nhiều cổng hơn router và cũng chuyển tiếp lưu lượng broadcast. Ngược lại, router không chuyển tiếp lưu lượng broadcast mặc định, điều này giúp giảm lưu lượng không cần thiết trên mạng.

#### 3. **Ví Dụ Về Hoạt Động Của Switch Và Router**
- **Mạng với Switches**: Trong một tòa nhà có các host được kết nối với các switch và đều nằm trong cùng một mạng con IP 10.10.10.0/24, các host này có thể giao tiếp với nhau mà không cần đến router. Tuy nhiên, nếu một host có địa chỉ IP thuộc mạng con khác (ví dụ: 10.10.11.0/24), thì nó không thể giao tiếp với các host trong mạng con 10.10.10.0/24 chỉ với switch. Để giao tiếp giữa các mạng con này, cần có một router để định tuyến lưu lượng giữa chúng.
- **Router Trong Mạng**: Khi đưa một router vào hệ thống, router này sẽ biết đến các mạng con 10.10.10.0/24 và 10.10.11.0/24 và sẽ định tuyến lưu lượng giữa các host thuộc các mạng con này, cho phép chúng giao tiếp với nhau.

#### 4. **Switch Layer 3 (Switch Định Tuyến)**
- Một số switch nâng cao có khả năng định tuyến và được gọi là **Layer 3 Switches**. Những switch này có khả năng nhận biết các địa chỉ IP và định tuyến lưu lượng giữa các mạng con khác nhau giống như router, nhưng chúng vẫn giữ nhiều đặc điểm của switch như hỗ trợ giao diện Ethernet và có nhiều cổng hơn so với router thông thường.
- Trong thực tế, **Layer 3 Switches** trở nên phổ biến vì giá thành của chúng đã giảm, và chúng có thể đảm nhận nhiệm vụ định tuyến lưu lượng nội bộ trong các mạng LAN.

Tuy nhiên, nếu mạng của bạn có kết nối ra bên ngoài đến một mạng diện rộng (WAN) và sử dụng các giao diện không phải là Ethernet (như ADSL hay Serial), bạn vẫn cần một router truyền thống để xử lý lưu lượng này.

### Tổng Kết:
Router và switch đều là các thành phần quan trọng trong mạng, nhưng chúng có vai trò và chức năng khác nhau. Router được sử dụng để định tuyến lưu lượng giữa các mạng con khác nhau, trong khi switch chủ yếu được sử dụng để chuyển tiếp lưu lượng giữa các thiết bị trong cùng một mạng LAN. Tuy nhiên, với sự phát triển của công nghệ, các switch hiện đại có thể đảm nhận một phần nhiệm vụ của router, giúp tối ưu hóa hiệu suất mạng.
