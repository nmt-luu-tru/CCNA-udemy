### Giới Thiệu Về Hub và Switch: Sự Khác Biệt và Cách Chúng Hoạt Động

Trong bài giảng này, bạn sẽ tìm hiểu về những kiến thức cơ bản về **hub** và **switch**, cũng như sự so sánh giữa chúng.

#### Hub Là Gì?

**Hub** là một thiết bị mạng đơn giản dùng để kết nối các thiết bị cuối trong mạng LAN (Local Area Network). Khi bạn cắm các thiết bị như PC, máy in, hoặc máy chủ vào hub qua cáp Ethernet, các thiết bị đó sẽ có thể giao tiếp với nhau thông qua hub. Hub hoạt động ở **Tầng 1** của mô hình OSI, tức là **Tầng Vật Lý** (Physical Layer). 

##### Đặc Điểm Của Hub:
- **Hoạt động ở chế độ bán song công (half-duplex)**: Điều này có nghĩa là các thiết bị kết nối vào hub chỉ có thể gửi hoặc nhận dữ liệu tại một thời điểm, không thể làm cả hai cùng lúc.
- **Chia sẻ cùng một miền va chạm (collision domain)**: Tất cả các thiết bị cắm vào hub đều chia sẻ chung một miền va chạm. Điều này nghĩa là chỉ có một thiết bị có thể truyền dữ liệu tại một thời điểm. Nếu hai thiết bị cùng truyền dữ liệu cùng lúc, sẽ xảy ra va chạm dữ liệu.
- **Phát hiện và xử lý va chạm**: Khi xảy ra va chạm, các thiết bị sẽ sử dụng phương pháp **CSMA/CD** (Carrier-Sense Multiple Access with Collision Detection) để phát hiện và xử lý va chạm. Thiết bị sẽ ngừng truyền, đợi một thời gian ngẫu nhiên và thử gửi lại dữ liệu sau đó.

#### Switch Là Gì?

**Switch** là thiết bị mạng cao cấp hơn so với hub. Nó cũng kết nối các thiết bị cuối trong mạng LAN, nhưng với những tính năng ưu việt hơn. Switch hoạt động ở **Tầng 2** của mô hình OSI, tức là **Tầng Liên Kết Dữ Liệu** (Data Link Layer). Tuy nhiên, nó cũng có chức năng của Tầng Vật Lý vì vẫn phải xử lý các cổng kết nối vật lý.

##### Đặc Điểm Của Switch:
- **Hoạt động ở chế độ song công toàn phần (full-duplex)**: Với chế độ này, các thiết bị kết nối vào switch có thể gửi và nhận dữ liệu cùng lúc, sử dụng các dây nhận và truyền riêng biệt.
- **Tạo ra các miền va chạm riêng biệt**: Mỗi thiết bị kết nối vào switch có miền va chạm riêng của nó, nghĩa là không xảy ra va chạm dữ liệu giữa các thiết bị. Do đó, không cần cơ chế phát hiện va chạm.
- **Nhận biết địa chỉ MAC**: Switch hoạt động ở Tầng 2, do đó, nó nhận biết được địa chỉ MAC của các thiết bị kết nối. Khi nhận một khung dữ liệu (frame), switch sẽ xem địa chỉ MAC nguồn (source MAC address) và học được rằng địa chỉ MAC đó có thể được truy cập từ cổng nào. Nó sẽ lưu trữ thông tin này trong **bảng địa chỉ MAC** (MAC address table). Nếu sau đó nhận một khung dữ liệu unicast với địa chỉ MAC đích đã biết, switch sẽ chỉ gửi khung đó đến đúng cổng, thay vì gửi đến tất cả các cổng như hub.

#### So Sánh Giữa Hub và Switch:
- **Hub**: 
  - Hoạt động ở Tầng 1 (Physical Layer).
  - Không nhận biết địa chỉ MAC.
  - Chỉ có thể hoạt động ở chế độ bán song công (half-duplex).
  - Chia sẻ cùng một miền va chạm cho tất cả các thiết bị.
  - Phát dữ liệu đến tất cả các cổng (flooding).

- **Switch**:
  - Hoạt động ở Tầng 2 (Data Link Layer) và Tầng 1 (Physical Layer).
  - Nhận biết địa chỉ MAC và lưu trữ thông tin này trong bảng địa chỉ MAC.
  - Hoạt động ở chế độ song công toàn phần (full-duplex), cho phép gửi và nhận dữ liệu đồng thời.
  - Mỗi thiết bị có miền va chạm riêng, không cần cơ chế phát hiện va chạm.
  - Chỉ gửi dữ liệu đến cổng đích cụ thể, trừ khi khung dữ liệu là broadcast hoặc unicast chưa biết.

#### Tương Lai Của Hub và Switch

Trong quá khứ, khoảng 15 năm trước, **hub** rất phổ biến vì **switch** khi đó có giá thành rất cao. Tuy nhiên, với sự giảm giá và tăng cường hiệu suất của switch, ngày nay, **hub** hầu như không còn được sử dụng và rất khó tìm mua. Các mạng LAN hiện đại chủ yếu sử dụng switch vì các lợi ích vượt trội về hiệu suất và bảo mật.
