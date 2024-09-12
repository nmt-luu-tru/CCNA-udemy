### DHCP Pool là gì?

**DHCP Pool** là một phạm vi địa chỉ IP mà DHCP server sử dụng để cấp phát cho các thiết bị (client) trong mạng. Khi một thiết bị kết nối vào mạng và yêu cầu một địa chỉ IP, DHCP server sẽ lấy một địa chỉ IP từ pool này để cấp phát cho thiết bị đó.

### Các Thành Phần của DHCP Pool:

1. **Range of IP Addresses**: Dải địa chỉ IP mà DHCP server sẽ cấp phát. Ví dụ: từ 192.168.1.100 đến 192.168.1.200.
2. **Subnet Mask**: Thông số này xác định phần nào của địa chỉ IP thuộc về mạng và phần nào thuộc về thiết bị trong mạng.
3. **Default Gateway**: Địa chỉ IP của router hoặc gateway mà thiết bị sử dụng để truy cập ra ngoài mạng nội bộ.
4. **DNS Servers**: Địa chỉ IP của các server DNS mà thiết bị sử dụng để phân giải tên miền.
5. **Lease Time**: Thời gian mà một thiết bị được phép sử dụng địa chỉ IP đã cấp trước khi cần phải gia hạn hoặc lấy một địa chỉ mới.

#### Default Gateway là gì?

**Default Gateway** là địa chỉ IP của một thiết bị mạng, thường là router, đóng vai trò là “cửa ngõ” mặc định để các thiết bị trong mạng nội bộ gửi dữ liệu ra ngoài. Khi một thiết bị cần gửi dữ liệu đến một địa chỉ IP nằm ngoài mạng nội bộ (không thuộc cùng subnet), dữ liệu sẽ được gửi đến Default Gateway trước. Router này sẽ quyết định cách thức chuyển tiếp gói dữ liệu ra ngoài mạng nội bộ, thường là đến Internet hoặc đến các mạng khác.

##### Ví dụ và Ý nghĩa:

Giả sử bạn có một mạng nội bộ với địa chỉ IP trong dải 192.168.1.0/24 (tức là từ 192.168.1.1 đến 192.168.1.254), và router của bạn có địa chỉ IP là 192.168.1.1. Khi một máy tính trong mạng (ví dụ: 192.168.1.10) muốn truy cập một trang web như www.google.com (có địa chỉ IP là 172.217.0.0), máy tính sẽ không thể gửi gói tin trực tiếp đến địa chỉ này vì nó nằm ngoài mạng nội bộ.

**Quá trình sử dụng Default Gateway diễn ra như sau:**

1. **Kiểm tra địa chỉ đích:** Máy tính kiểm tra xem địa chỉ IP đích (172.217.0.0) có thuộc mạng nội bộ không (192.168.1.0/24).
   
2. **Gửi đến Default Gateway:** Nếu địa chỉ đích không thuộc mạng nội bộ, máy tính sẽ gửi gói tin đến Default Gateway (192.168.1.1).

3. **Chuyển tiếp từ Default Gateway:** Router nhận gói tin và kiểm tra địa chỉ đích. Nó sẽ quyết định gửi gói tin đó ra ngoài, thông qua kết nối với Internet hoặc một mạng khác.

4. **Đến đích:** Gói tin sẽ đi qua nhiều router khác trên Internet trước khi đến địa chỉ IP đích của trang web.

##### Tại sao Default Gateway quan trọng?

- **Kết nối với mạng bên ngoài:** Default Gateway cho phép các thiết bị trong mạng nội bộ kết nối với các mạng bên ngoài, như Internet. Nếu không có Default Gateway, các thiết bị chỉ có thể giao tiếp với nhau trong cùng một mạng.
  
- **Quản lý lưu lượng:** Router làm Default Gateway có thể quản lý và điều khiển lưu lượng ra vào mạng nội bộ, bao gồm việc áp dụng các chính sách bảo mật, lọc dữ liệu, hoặc ưu tiên băng thông.

- **Đơn giản hóa cấu hình:** Thay vì phải cấu hình thủ công các tuyến đường (routes) cho từng đích cụ thể, Default Gateway giúp tự động hóa quá trình này bằng cách cung cấp một đường dẫn mặc định cho các gói tin.

Nói một cách đơn giản, Default Gateway giống như cánh cửa chính dẫn từ nhà bạn (mạng nội bộ) ra thế giới bên ngoài (Internet), nơi tất cả các giao tiếp với bên ngoài sẽ phải đi qua.  

#### DNS Servers là gì?

**DNS (Domain Name System) Servers** là các máy chủ thực hiện chức năng chuyển đổi (phân giải) tên miền thành địa chỉ IP tương ứng để các thiết bị có thể giao tiếp qua mạng. Các thiết bị trong mạng, như máy tính, điện thoại, và các thiết bị IoT, sử dụng địa chỉ IP để xác định và kết nối với nhau. Tuy nhiên, con người lại quen thuộc với tên miền (như www.google.com) hơn là các dãy số của địa chỉ IP (như 172.217.0.0).  

Chúng ta biết rằng, các nút mạng cần có địa chỉ IP để định danh cho chúng trên môi trường liên mạng như mạng Internet, trong đó các server cung cấp dịch vụ không phải là một ngoại lệ. Địa chỉ IP này được sử dụng làm địa chỉ cho quá trình truyền tin như chúng ta đã được học về giao thức IP. Nghĩa là khi người dùng muốn truy cập dịch vụ trên một server nào đó, họ sẽ phải cung cấp cho phần mềm client địa chỉ IP của server đó.

Điều này thật sự là bất tiện vì địa chỉ IP là một chuỗi 4 con số, không phải là điều dễ nhớ cho người dùng. Vì vậy, người ta còn sử dụng tên miền(domain name) là một chuỗi ký tự có tính gợi nhớ hơn cho người dùng để đặt định danh cho server. Như vậy, chúng ta cần có một hệ thống quản lý các tên miền này cũng như cung cấp dịch vụ cho các phần mềm client tìm thông tin địa chỉ IP khi đã biết tên miền của server. 

DNS là viết tắt của cụm từ Domain Name System, mang ý nghĩa đầy đủ là hệ thống phân giải tên miền. Hiểu một cách ngắn gọn nhất, DNS cơ bản là một hệ thống chuyển đổi một địa chỉ IP dạng số sang các tên miền website tương ứng mà chúng ta đang sử dụng, ở dạng www...com và ngược lại.

Ngoài việc giúp con người có thể sử dụng các tên miền dễ nhớ hơn, DNS cung cấp tính năng trỏ tên miền đến các máy chủ theo các khu vực địa lý khác nhau. Đối với các website lớn, thay vì giữ tất cả máy chủ web ở cùng một chỗ, họ phân phối hệ thống máy chủ của họ trải khắp toàn cầu. Khi đó, DNS sẽ giúp các bạn trỏ đến các IP của máy chủ trong khu vực của bạn thông qua tên miền, giúp cho việc truy cập web trở nên nhanh và tiện lợi hơn. Đây được gọi là cơ chế phân phối DNS.

##### Vai trò của DNS Servers:

Khi bạn nhập một tên miền vào trình duyệt, thiết bị của bạn không hiểu ngay tên miền đó, vì nó cần địa chỉ IP để kết nối. Đây là lúc DNS server vào cuộc:

1. **Phân giải tên miền**: DNS server nhận yêu cầu từ thiết bị của bạn để phân giải tên miền thành địa chỉ IP. Ví dụ, khi bạn nhập "www.google.com," DNS server sẽ trả về địa chỉ IP tương ứng, như 172.217.0.0.

2. **Kết nối với địa chỉ IP**: Sau khi nhận được địa chỉ IP, thiết bị của bạn sẽ sử dụng nó để kết nối với máy chủ của trang web mà bạn muốn truy cập.

##### Quá trình phân giải tên miền:

1. **Yêu cầu từ thiết bị**: Khi bạn nhập một tên miền vào trình duyệt, thiết bị của bạn sẽ gửi một yêu cầu đến DNS server mà nó được cấu hình để sử dụng. Thông thường, các DNS server này được cung cấp tự động qua DHCP hoặc được cấu hình thủ công.

2. **Tìm kiếm và phản hồi**: DNS server kiểm tra trong cơ sở dữ liệu của nó để tìm địa chỉ IP phù hợp với tên miền. Nếu DNS server không có thông tin này, nó sẽ chuyển tiếp yêu cầu đến các DNS server khác, có thể là các DNS server gốc, hoặc các DNS server khác trong hệ thống phân cấp của DNS.

3. **Trả về địa chỉ IP**: Sau khi tìm thấy địa chỉ IP phù hợp, DNS server sẽ trả lời thiết bị của bạn với địa chỉ IP đó.

4. **Kết nối**: Thiết bị của bạn sử dụng địa chỉ IP nhận được để kết nối đến máy chủ đích và bắt đầu trao đổi dữ liệu.

##### Ví dụ về DNS Server:

- **DNS của Google**: Một trong những DNS server phổ biến nhất là của Google với địa chỉ IP 8.8.8.8 và 8.8.4.4. Nhiều người dùng và doanh nghiệp sử dụng DNS của Google vì tốc độ và độ tin cậy cao.
  
- **DNS của nhà cung cấp dịch vụ Internet (ISP)**: Thường khi bạn kết nối Internet, ISP của bạn sẽ cung cấp DNS server mặc định cho thiết bị của bạn thông qua DHCP. Những DNS server này thường nằm gần bạn về mặt địa lý, giúp quá trình phân giải tên miền diễn ra nhanh chóng.

##### Tại sao DNS Servers quan trọng?

- **Dễ nhớ**: Con người dễ nhớ tên miền (như www.google.com) hơn là các chuỗi số của địa chỉ IP. DNS servers giúp người dùng dễ dàng truy cập các trang web bằng tên miền thay vì phải nhớ các địa chỉ IP phức tạp.
  
- **Quản lý tập trung**: DNS servers cho phép quản lý tập trung việc phân giải tên miền, giúp mạng Internet hoạt động một cách mạch lạc và hiệu quả.

- **Tốc độ truy cập**: DNS servers nhanh và hiệu quả sẽ giúp tăng tốc độ truy cập trang web, vì quá trình phân giải tên miền diễn ra nhanh hơn.

- **An ninh**: Một số DNS servers cung cấp thêm các tính năng bảo mật, như lọc các trang web độc hại hoặc bảo vệ người dùng khỏi các cuộc tấn công mạng dựa trên DNS.

Nói một cách đơn giản, DNS servers giống như một danh bạ điện thoại cho Internet, giúp chuyển đổi tên miền mà con người sử dụng thành địa chỉ IP mà máy tính sử dụng để giao tiếp.

### Ví Dụ Cấu Hình DHCP Pool

Giả sử bạn đang cấu hình một DHCP server trên router với các thông số sau:

- Dải địa chỉ IP từ 192.168.10.100 đến 192.168.10.150
- Subnet mask: 255.255.255.0
- Default gateway: 192.168.10.1
- DNS server: 8.8.8.8 (Google DNS)
- Lease time: 12 giờ

Dưới đây là một ví dụ cấu hình cơ bản trên một router Cisco:

```bash
Router(config)# ip dhcp pool LAN1
Router(dhcp-config)# network 192.168.10.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.10.1
Router(dhcp-config)# dns-server 8.8.8.8
Router(dhcp-config)# lease 12
Router(dhcp-config)# exit
Router(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.99
Router(config)# ip dhcp excluded-address 192.168.10.151 192.168.10.254
```

- **ip dhcp pool LAN**: Tạo một DHCP pool với tên 'LAN1'.
- **network 192.168.10.0 255.255.255.0**: Xác định dải mạng mà DHCP sẽ quản lý.
- **default-router 192.168.10.1**: Cài đặt địa chỉ gateway mặc định.
- **dns-server 8.8.8.8**: Cài đặt địa chỉ server DNS.
- **lease 12**: Đặt thời gian lease là 12 giờ.
- **ip dhcp excluded-address**: Loại bỏ các địa chỉ IP mà DHCP không được cấp phát (thường là dành cho các thiết bị cần IP cố định như server, router).
