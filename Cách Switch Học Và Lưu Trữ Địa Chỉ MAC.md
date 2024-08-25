### Hoạt Động Của Switch Trong Mạng: Tìm Hiểu Chi Tiết Về Cách Switch Học Và Lưu Trữ Địa Chỉ MAC

Trong bài giảng này, chúng ta sẽ tìm hiểu chi tiết hơn về cách mà **switch** hoạt động tại Tầng 2 của mô hình OSI, cụ thể là cách nó học và lưu trữ các địa chỉ MAC vào **bảng địa chỉ MAC** (MAC address table) thông qua một ví dụ minh họa.

#### Ví Dụ 1: Hoạt Động Của Một Switch Đơn Lẻ

Giả sử chúng ta có một switch với ba thiết bị đầu cuối (host) được kết nối:

- **Host 1** có địa chỉ MAC là 1.1.1.1, cắm vào Port 1 của switch.
- **Host 2** có địa chỉ MAC là 2.2.2.2, cắm vào Port 2.
- **Host 3** có địa chỉ MAC là 3.3.3.3, cắm vào Port 3.

Hiện tại, switch vừa được bật nguồn, vì vậy bảng địa chỉ MAC chưa có thông tin gì.

- **Bước 1**: **Host 1** gửi một khung dữ liệu (frame) có địa chỉ MAC đích là 2.2.2.2. Switch nhận được khung dữ liệu này và thấy rằng khung dữ liệu có địa chỉ MAC nguồn là 1.1.1.1. Switch sẽ học được rằng **Host 1** có thể được truy cập thông qua **Port 1**, và ghi nhận thông tin này vào bảng địa chỉ MAC. Tuy nhiên, vì địa chỉ MAC đích (2.2.2.2) chưa có trong bảng, switch sẽ **flood** (gửi tràn) khung dữ liệu ra tất cả các cổng khác, trừ cổng mà nó nhận được.
  
- **Bước 2**: **Host 2** nhận được khung dữ liệu, nhận thấy rằng địa chỉ MAC đích là của chính nó, nên sẽ phản hồi lại **Host 1**. Switch tiếp tục học được rằng **Host 2** có thể được truy cập qua **Port 2** và cập nhật bảng địa chỉ MAC. Lần này, khi chuyển tiếp khung dữ liệu, switch sẽ gửi nó trực tiếp đến **Port 1** vì đã biết rằng **Host 1** có thể được truy cập qua đó.

#### Ví Dụ 2: Hoạt Động Trong Mạng Có Nhiều Switch

Giả sử mạng của chúng ta có hai switch được kết nối với nhau:

- **Switch 1** có **Host 1** (1.1.1.1) cắm vào **Port 1** và **Host 2** (2.2.2.2) cắm vào **Port 2**.
- **Switch 2** có **Host 3** (3.3.3.3) cắm vào **Port 1** và **Host 4** (4.4.4.4) cắm vào **Port 2**.

Hai switch này được kết nối với nhau qua **Port 24** trên mỗi switch.

- **Bước 1**: **Host 1** gửi một khung dữ liệu với địa chỉ MAC đích là 2.2.2.2. **Switch 1** học được rằng **Host 1** nằm ở **Port 1** và thêm vào bảng địa chỉ MAC của nó. Khung dữ liệu sau đó được flood ra tất cả các cổng, bao gồm **Port 2** và **Port 24** (kết nối đến **Switch 2**).

- **Bước 2**: Khi khung dữ liệu đến **Switch 2**, switch này sẽ tiếp tục flood ra tất cả các cổng. Các host khác sẽ bỏ qua khung dữ liệu nếu địa chỉ MAC đích không phải của chúng. **Switch 2** cũng học được rằng **Host 1** nằm ở **Port 24**. Khi **Host 2** phản hồi lại **Host 1**, **Switch 1** sẽ biết rằng **Host 2** nằm ở **Port 2** và chuyển tiếp trực tiếp khung dữ liệu qua **Port 1**.

- **Bước 3**: Nếu **Host 3** gửi dữ liệu đến **Host 2**, **Switch 2** sẽ học được rằng **Host 3** nằm ở **Port 1** và flood khung dữ liệu ra tất cả các cổng, bao gồm cả **Port 24** đến **Switch 1**. **Switch 1** sau đó sẽ chuyển tiếp khung dữ liệu trực tiếp đến **Host 2**.

#### Kết Luận

Thông qua hai ví dụ trên, bạn có thể thấy cách mà các switch học và lưu trữ các địa chỉ MAC vào bảng địa chỉ MAC của chúng. Với một switch đơn lẻ, việc học và lưu trữ địa chỉ diễn ra nhanh chóng và dễ dàng. Trong một mạng có nhiều switch, các switch sẽ giao tiếp với nhau thông qua các cổng kết nối và chia sẻ thông tin về các địa chỉ MAC mà chúng đã học được. Điều này giúp tối ưu hóa luồng dữ liệu, tránh tình trạng "flood" không cần thiết và cải thiện hiệu suất của toàn mạng.
