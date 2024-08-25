### Tìm Hiểu về Các Hệ Điều Hành Trên Các Thiết Bị Cisco

Trong bài học này, chúng ta sẽ tìm hiểu về các hệ điều hành khác nhau được sử dụng trên các nền tảng router và switch của Cisco. Mặc dù thông tin này không xuất hiện trong kỳ thi, nhưng nó rất hữu ích trong việc hiểu biết tổng quan về các hệ điều hành mà Cisco sử dụng.

### 1. **Lịch Sử và Phát Triển Của Cisco**

Nhiều người nghĩ rằng Cisco là một công ty chuyên về routing và switching. Tuy nhiên, khi mới thành lập, Cisco chỉ tập trung vào routing. Hệ điều hành ban đầu mà Cisco sử dụng trên các router là **IOS (Internetwork Operating System)**, và đây cũng là hệ điều hành vẫn đang được sử dụng cho đến ngày nay, mặc dù đã trải qua nhiều nâng cấp kể từ khi Cisco được thành lập vào năm 1984.

### 2. **Mở Rộng Sang Switch và Các Thiết Bị Khác**

Để cung cấp các thiết bị switch, Cisco đã mua lại công ty Crescendo vào năm 1993, và từ đó, dòng sản phẩm switch Catalyst được ra đời. Hệ điều hành ban đầu trên các switch Catalyst là **CatOS**, nhưng hệ điều hành này đã bị loại bỏ từ lâu.

Ngoài ra, Cisco cũng đã mở rộng sang các thiết bị firewall thông qua việc mua lại Network Translation vào năm 1995. Từ thương vụ này, Cisco có được sản phẩm tường lửa PIX, sử dụng hệ điều hành **Finesse**.

Tuy nhiên, qua nhiều năm, Cisco đã chuẩn hóa và đưa các thiết bị này về sử dụng hệ điều hành IOS. Điều này giúp thống nhất quản lý và điều hành trên tất cả các thiết bị mạng của Cisco.

### 3. **Các Hệ Điều Hành Mới Hơn trên Nền Tảng Mới**

Mặc dù IOS vẫn chạy trên phần lớn các router và switch của Cisco, một số nền tảng mới hơn đã chuyển sang các hệ điều hành khác như:

- **NX-OS**: Được sử dụng trên các switch Nexus và MDS trong các trung tâm dữ liệu.
- **IOS-XR**: Được sử dụng trên các router cao cấp dành cho nhà cung cấp dịch vụ như NCS, CRS, ASR9000, và XR12000.
- **IOS-XE**: Được sử dụng trên các router ASR1000 dành cho nhà cung cấp dịch vụ.

### 4. **Sự Tương Đồng và Khác Biệt**

Mặc dù có nhiều hệ điều hành khác nhau, các lệnh quản lý và cấu hình giữa chúng rất giống nhau. Nếu bạn đã quen với các lệnh trong IOS, bạn sẽ thấy rằng các lệnh này cũng sẽ hoạt động tương tự trên các hệ điều hành khác như NX-OS hay IOS-XR. Điều này giúp giảm bớt sự phức tạp khi chuyển đổi giữa các hệ điều hành.

### 5. **Lý Do Có Nhiều Hệ Điều Hành**

Mặc dù các lệnh quản lý tương tự nhau, các hệ điều hành này khác nhau ở cấp độ kiến trúc bên trong. **IOS** sử dụng **monolithic kernel** (hạt nhân đơn khối), nghĩa là nếu một quá trình trên router gặp sự cố, nó có thể làm toàn bộ router bị treo. Trong khi đó, các hệ điều hành mới hơn sử dụng **microkernel** (hạt nhân vi mô), nơi các quá trình chạy trong các không gian bộ nhớ riêng biệt và được bảo vệ. Do đó, nếu một quá trình gặp sự cố, nó không ảnh hưởng đến các phần còn lại của hệ thống.

### 6. **Độ Tin Cậy của IOS**

Mặc dù có sự khác biệt về kiến trúc, không nên nghĩ rằng IOS là một hệ điều hành kém tin cậy. Cisco đã phát triển và cải tiến IOS trong nhiều năm, biến nó thành một hệ điều hành cứng cáp và rất đáng tin cậy, đặc biệt trên các thiết bị router và switch cấp doanh nghiệp.

### **Kết Luận**

Việc hiểu rõ về các hệ điều hành khác nhau trên các thiết bị Cisco sẽ giúp bạn tự tin hơn trong việc quản lý và cấu hình các thiết bị mạng. Mặc dù có nhiều hệ điều hành khác nhau, sự tương đồng trong cách quản lý và vận hành giữa chúng giúp quá trình chuyển đổi và làm việc trở nên dễ dàng hơn.
