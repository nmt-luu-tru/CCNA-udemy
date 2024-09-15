Thông thường, mỗi **switch** và **router** chỉ có **một cổng console** duy nhất. Cổng console này được sử dụng để kết nối trực tiếp vào thiết bị, cho phép quản trị viên thực hiện cấu hình ban đầu hoặc khắc phục sự cố. Đây là cách kết nối cơ bản và không yêu cầu thiết bị đã được cấu hình trước đó.

**Chi tiết về cổng console trên switch và router:**

- **Cổng console** thường là cổng RJ-45 (nhìn giống cổng mạng) hoặc có thể là cổng mini-USB trên các thiết bị mới hơn.
- Việc sử dụng cổng console đòi hỏi cáp console (cáp màu xanh dương truyền thống với đầu RJ-45 hoặc USB) để kết nối với máy tính của quản trị viên.
- Phần mềm như PuTTY, Tera Term, hoặc HyperTerminal thường được sử dụng trên máy tính để truy cập giao diện dòng lệnh của thiết bị qua cổng console.

Mặc dù mỗi thiết bị chỉ có một cổng console, một số thiết bị cao cấp có thể hỗ trợ thêm cổng **auxiliary (AUX)**, nhưng cổng này chủ yếu được sử dụng cho kết nối từ xa qua modem hoặc cho mục đích khắc phục sự cố, không phải là cổng console chính.

---
Cổng console trên switch hoặc router được thiết kế để kết nối với máy tính của quản trị viên hoặc một thiết bị đầu cuối khác nhằm mục đích cấu hình, quản lý và khắc phục sự cố thiết bị mạng. 

**Cụ thể, cổng console kết nối với:**

1. **Máy tính của quản trị viên**:
   - Đây là cách kết nối phổ biến nhất. Quản trị viên sử dụng máy tính xách tay hoặc máy tính để bàn để kết nối trực tiếp với cổng console của switch hoặc router.
   
2. **Cáp console**:
   - Kết nối này sử dụng một cáp console đặc biệt, thường là cáp màu xanh dương với một đầu RJ-45 cắm vào cổng console của switch/router và đầu còn lại là đầu nối DB-9 (RS-232) hoặc USB cắm vào máy tính của quản trị viên.
   - Trên các thiết bị mới hơn, cáp console có thể sử dụng đầu mini-USB thay vì đầu RJ-45.

3. **Phần mềm terminal**:
   - Để tương tác với thiết bị qua cổng console, máy tính cần cài đặt phần mềm terminal như PuTTY, Tera Term, HyperTerminal, hoặc các phần mềm tương tự. Phần mềm này cho phép quản trị viên nhập lệnh cấu hình và xem thông tin từ thiết bị.

4. **Thiết bị đầu cuối hoặc máy in đầu cuối**:
   - Trong một số môi trường lớn hơn hoặc phức tạp hơn, cổng console có thể kết nối với thiết bị đầu cuối hoặc máy in đầu cuối, nhưng đây không phải là cách thông dụng hiện nay.

Kết nối qua cổng console thường được sử dụng cho các mục đích như cấu hình ban đầu, khắc phục sự cố, hoặc khi không thể truy cập vào thiết bị qua các phương tiện mạng khác như Telnet hoặc SSH.  

Vì vậy phải cấu hình bảo mật truy cập trên dòng console của switch hoặc router, giúp bảo vệ thiết bị khỏi truy cập trái phép thông qua cổng console.
---
