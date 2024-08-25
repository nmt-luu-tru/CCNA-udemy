### Tìm Hiểu Về Subnet Mask

Trong bài giảng này, bạn sẽ học về **subnet mask** và cách nó hoạt động trong việc phân chia mạng con trong mạng IP.

#### 1. Các Thông Tin Cơ Bản

Mỗi thiết bị trong mạng đều biết địa chỉ IP của mình, **subnet mask**, và **default gateway**.

Ví dụ:
- Địa chỉ IP: **192.168.10.15**
- Subnet Mask: **255.255.255.0**
- Default Gateway: **192.168.10.1**

Subnet mask giúp xác định phần nào trong địa chỉ IP là **network** (mạng) và phần nào là **host** (máy chủ).

#### 2. Giao Tiếp Trong Mạng

- **Cùng Subnet**: Các thiết bị trong cùng một subnet có thể gửi và nhận dữ liệu trực tiếp thông qua switch mà không cần đi qua router.
  
- **Khác Subnet**: Nếu một thiết bị muốn giao tiếp với thiết bị ở subnet khác, dữ liệu phải đi qua router (được gọi là **default gateway**).

Thiết bị sẽ so sánh địa chỉ IP đích với địa chỉ IP của mình và subnet mask để xác định xem địa chỉ đích có nằm trong cùng subnet hay không.

#### 3. Cách Hoạt Động Của Subnet Mask

**Subnet mask** cũng dài 32 bit như địa chỉ IP và có thể được viết dưới dạng thập phân có dấu chấm hoặc dạng **slash (/) notation**.

Ví dụ:
- Địa chỉ IP: **192.168.10.15**
- Subnet Mask: **255.255.255.0**

Ta có thể viết cả địa chỉ IP và subnet mask dưới dạng nhị phân:

- Địa chỉ IP: 11000000.10101000.00001010.00001111
- Subnet Mask: 11111111.11111111.11111111.00000000

Các bit '1' trong subnet mask chỉ ra phần **network** của địa chỉ IP, và các bit '0' chỉ ra phần **host**.

Trong ví dụ trên, phần network là **192.168.10** và phần host là **15**.

#### 4. Cách Xác Định Subnet

Nếu hai địa chỉ IP có phần **network** giống nhau, chúng thuộc cùng một subnet. Ví dụ, các địa chỉ IP sau đều nằm trong cùng subnet:

- **192.168.10.15**
- **192.168.10.20**

Nếu địa chỉ đích khác subnet (ví dụ: **192.168.11.20**), thiết bị sẽ gửi dữ liệu qua router.

#### 5. Subnet Mask Hợp Lệ

Subnet mask phải bắt đầu bằng một dãy bit '1' liên tục, sau đó là các bit '0'. Ví dụ:

- **11111111.11111111.11111111.00000000** là hợp lệ.
- **11101101.11110000.11110000.00000000** là không hợp lệ.

#### 6. Phần Host Của Địa Chỉ IP

Phần **host** của địa chỉ IP có thể được gán cho các thiết bị trong mạng như PC, server, máy in, v.v. Tuy nhiên, có hai ngoại lệ:

1. **All 0's** trong phần host: Địa chỉ này biểu thị **network address** và không thể được gán cho thiết bị.
  
   - Ví dụ: **192.168.10.0**

2. **All 1's** trong phần host: Địa chỉ này là **directed broadcast address** và cũng không thể được gán cho thiết bị.

   - Ví dụ: **192.168.10.255**

#### 7. Phạm Vi Địa Chỉ Có Thể Sử Dụng

Trong ví dụ với **192.168.10.0/24**, các địa chỉ có thể được sử dụng cho các thiết bị trong mạng là từ **192.168.10.1** đến **192.168.10.254**.

### Kết Luận

Việc hiểu về subnet mask và cách nó hoạt động trong việc phân chia mạng là rất quan trọng để quản lý và thiết kế mạng IP hiệu quả. Điều này sẽ giúp bạn xác định đúng các subnet trong mạng và cấu hình chúng một cách chính xác.
