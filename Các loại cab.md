Trong Cisco Packet Tracer, khi bạn chọn **“Connections”** (biểu tượng tia sét), bạn sẽ thấy các loại cáp khác nhau có sẵn để kết nối các thiết bị mạng. Mỗi loại cáp phục vụ cho mục đích kết nối cụ thể giữa các thiết bị khác nhau. Dưới đây là các loại cáp phổ biến mà bạn sẽ thấy trong Packet Tracer:

### 1. **Automatic (Auto-Choose Connection Type)**
   - **Biểu tượng**: Một tia sét với màu xanh.
   - **Mô tả**: Packet Tracer sẽ tự động chọn loại cáp phù hợp dựa trên hai thiết bị bạn muốn kết nối. Nếu bạn không chắc chắn nên sử dụng loại cáp nào, đây là lựa chọn tốt nhất.

### 2. **Copper Straight-Through**
   - **Biểu tượng**: Dây cáp với đầu màu xanh lá cây.
   - **Mô tả**: Sử dụng để kết nối các thiết bị khác loại, như Router với Switch, Switch với PC, hoặc Router với PC.
   - **Sử dụng**: Kết nối Router với Switch, Switch với PC, hoặc các thiết bị đầu cuối với nhau.

### 3. **Copper Cross-Over**
   - **Biểu tượng**: Dây cáp với đầu màu đỏ.
   - **Mô tả**: Sử dụng để kết nối các thiết bị cùng loại với nhau, như Switch với Switch, Router với Router, hoặc PC với PC.
   - **Sử dụng**: Kết nối hai Switch, hai Router, hoặc hai PC với nhau.

### 4. **Fiber Optic**
   - **Biểu tượng**: Dây cáp với đầu màu cam.
   - **Mô tả**: Sử dụng để kết nối các thiết bị qua khoảng cách xa với tốc độ cao hơn, thường là giữa hai Switch có cổng GigabitEthernet hoặc cổng quang học (SFP).
   - **Sử dụng**: Kết nối giữa các Switch hỗ trợ cổng quang học, hoặc giữa Router và Switch có cổng quang học.

### 5. **Serial DCE (Data Communication Equipment)**
   - **Biểu tượng**: Dây cáp với đầu màu đen với một ký hiệu đồng hồ.
   - **Mô tả**: Sử dụng để kết nối giữa hai Router trong các mô phỏng mạng WAN, với một đầu là DCE cung cấp đồng hồ (clock rate).
   - **Sử dụng**: Kết nối hai Router với nhau trên cổng Serial, với đầu DCE cắm vào cổng có cấu hình clock rate.

### 6. **Serial DTE (Data Terminal Equipment)**
   - **Biểu tượng**: Dây cáp với đầu màu đen mà không có ký hiệu đồng hồ.
   - **Mô tả**: Sử dụng kết hợp với cáp Serial DCE để kết nối hai Router, với đầu DTE cắm vào cổng không cấu hình clock rate.
   - **Sử dụng**: Kết nối hai Router với nhau trên cổng Serial, với đầu DTE cắm vào cổng không có cấu hình clock rate.

### 7. **Coaxial**
   - **Biểu tượng**: Dây cáp với đầu màu đen với một vòng tròn vàng.
   - **Mô tả**: Sử dụng trong các kết nối mạng cũ hoặc mạng truyền hình cáp, thường không phổ biến trong các cấu hình hiện đại.
   - **Sử dụng**: Kết nối các thiết bị sử dụng cáp đồng trục, như mạng truyền hình cáp.

### 8. **Phone**
   - **Biểu tượng**: Dây cáp với đầu màu đen với một ký hiệu điện thoại.
   - **Mô tả**: Sử dụng để kết nối các thiết bị điện thoại hoặc mô phỏng mạng VoIP (Voice over IP).
   - **Sử dụng**: Kết nối điện thoại IP với router hoặc switch trong các mô hình mạng VoIP.

### 9. **Console**
   - **Biểu tượng**: Dây cáp với đầu màu xanh dương.
   - **Mô tả**: Sử dụng để kết nối từ cổng console của router hoặc switch đến cổng COM trên PC để quản lý thiết bị qua giao diện dòng lệnh (CLI).
   - **Sử dụng**: Kết nối PC với cổng console của Router hoặc Switch để cấu hình thiết bị qua CLI.

### 10. **Octal**
   - **Biểu tượng**: Dây cáp với đầu nhiều nhánh.
   - **Mô tả**: Sử dụng để kết nối nhiều thiết bị từ một cổng serial quản lý (một đầu nối nhiều đầu còn lại).
   - **Sử dụng**: Quản lý nhiều thiết bị thông qua một cổng serial.

### **Sử dụng đúng loại cáp rất quan trọng** trong Cisco Packet Tracer để đảm bảo rằng các thiết bị có thể giao tiếp với nhau một cách chính xác. Nếu bạn không chắc chắn về loại cáp nào cần sử dụng, bạn có thể chọn chế độ **Auto** để Packet Tracer tự động chọn cáp phù hợp cho bạn.
