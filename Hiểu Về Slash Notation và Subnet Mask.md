### Hiểu Về Slash Notation và Subnet Mask

Trong bài giảng này, bạn sẽ học cách biểu diễn **subnet mask** dưới dạng **slash notation** và hiểu rõ hơn về ý nghĩa của chúng.

#### 1. Biểu Diễn Subnet Mask

Subnet mask có thể được viết dưới dạng **dotted decimal notation** (ví dụ: **255.255.255.0**) hoặc dưới dạng **slash notation** (ví dụ: **/24**).

- **255.255.255.0** có 24 bit đầu là **1** và 8 bit cuối là **0**. Do đó, nó có thể được viết tắt là **/24**.
- **255.255.0.0** có 16 bit đầu là **1** và 16 bit cuối là **0**, và có thể được viết tắt là **/16**.

#### 2. Lợi Ích Của Slash Notation

**Slash notation** đơn giản và gọn gàng hơn so với **dotted decimal notation**. Khi giao tiếp hoặc tạo sơ đồ mạng, chúng ta thường dùng slash notation vì nó ngắn gọn hơn và dễ đọc hơn.

Ví dụ:

- **255.255.255.0** có thể được viết là **/24**.
- **255.0.0.0** có thể được viết là **/8**.

#### 3. Ví Dụ Về Slash Notation

Xét một ví dụ cụ thể:

- Địa chỉ IP: **10.10.10.15**
- Subnet mask: **255.0.0.0**

Subnet mask này có 8 bit đầu là **1**, do đó có thể viết dưới dạng **/8**. Khi biểu diễn địa chỉ mạng:

- Địa chỉ mạng sẽ là **10.0.0.0/8**.
- Dải địa chỉ IP có thể sử dụng cho các thiết bị (hosts) trong mạng này sẽ từ **10.0.0.1** đến **10.255.255.254**.

- **10.255.255.255** không được sử dụng vì nó là địa chỉ broadcast, và **10.0.0.0** là địa chỉ mạng.

#### 4. Kết Luận

Việc hiểu cách sử dụng **slash notation** không chỉ giúp bạn làm việc hiệu quả hơn mà còn giúp bạn dễ dàng nhận ra cấu trúc mạng khi nhìn vào địa chỉ IP và subnet mask. Bạn sẽ ngày càng quen thuộc với việc phân biệt giữa phần **network** và **host** của địa chỉ IP khi làm việc với subnet mask.
