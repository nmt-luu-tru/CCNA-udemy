Dựa trên cấu trúc tổ chức của công ty IT với tổng số nhân viên là 52 người, dưới đây là số lượng host (địa chỉ IP) cần thiết cho từng phòng ban, bao gồm cả các thiết bị bổ sung như máy in, server, và thiết bị mạng khác:

### 1. **Phòng Điều hành và Hành chính (Executive & Administration)**
- **Số nhân viên:** 8 người
- **Thiết bị bổ sung:** 1 máy in, 1 server nhỏ (nếu cần cho quản lý tài liệu)
- **Tổng số host cần thiết:** 8 (PC) + 1 (máy in) + 1 (server) = **10 host**

### 2. **Phòng Phát triển Sản phẩm (Product Development)**
- **Số nhân viên:** 16 người
- **Thiết bị bổ sung:** 2 server (1 server cho phát triển ứng dụng, 1 server cho quản lý mã nguồn), 1 máy in
- **Tổng số host cần thiết:** 16 (PC) + 2 (server) + 1 (máy in) = **19 host**

### 3. **Phòng Kinh doanh và Marketing (Sales & Marketing)**
- **Số nhân viên:** 16 người
- **Thiết bị bổ sung:** 1 máy in, có thể thêm 1 server cho quản lý CRM hoặc dữ liệu khách hàng.
- **Tổng số host cần thiết:** 16 (PC) + 1 (máy in) + 1 (server) = **18 host**

### 4. **Phòng Công nghệ Thông tin và Hỗ trợ (IT & Tech Support)**
- **Số nhân viên:** 12 người
- **Thiết bị bổ sung:** 1 server cho quản trị mạng (có thể bao gồm các dịch vụ như DNS, DHCP), 1 máy in.
- **Tổng số host cần thiết:** 12 (PC) + 1 (server) + 1 (máy in) = **14 host**

### **Tổng kết số host cần thiết cho toàn công ty:**
- **Phòng Điều hành và Hành chính:** 10 host
- **Phòng Phát triển Sản phẩm:** 19 host
- **Phòng Kinh doanh và Marketing:** 18 host
- **Phòng Công nghệ Thông tin và Hỗ trợ:** 14 host

**Tổng số host cho toàn công ty:** 10 + 19 + 18 + 14 = **61 host**

### **Chú ý:**
- Tổng số host này bao gồm cả nhân viên và các thiết bị bổ sung cần thiết cho mỗi phòng ban.
- Số lượng host được tính rộng rãi để đảm bảo đủ cho các thiết bị bổ sung hoặc dự phòng cho các thiết bị tương lai.
- Nếu cần dự phòng hoặc mở rộng, có thể dự trù thêm khoảng 10-20% số host để đảm bảo không thiếu địa chỉ IP trong tương lai.
---
Dưới đây là chi tiết tính toán dự trù 20% số lượng host cho từng phòng ban:

### 1. **Phòng Điều hành và Hành chính (Executive & Administration)**
- Số host cần thiết ban đầu: 10 host
- Dự trù thêm 20%: 10 x 0.20 = 2 host
- Tổng số host sau dự trù: 10 + 2 = 12 host

### 2. **Phòng Phát triển Sản phẩm (Product Development)**
- Số host cần thiết ban đầu: 19 host
- Dự trù thêm 20%: 19 x 0.20 = 3.8 host
- Làm tròn lên: 4 host
- Tổng số host sau dự trù: 19 + 4 = 23 host

### 3. **Phòng Kinh doanh và Marketing (Sales & Marketing)**
- Số host cần thiết ban đầu: 18 host
- Dự trù thêm 20%: 18 x 0.20 = 3.6 host
- Làm tròn lên: 4 host
- Tổng số host sau dự trù: 18 + 4 = 22 host

### 4. **Phòng Công nghệ Thông tin và Hỗ trợ (IT & Tech Support)**
- Số host cần thiết ban đầu: 14 host
- Dự trù thêm 20%: 14 x 0.20 = 2.8 host
- Làm tròn lên: 3 host
- Tổng số host sau dự trù: 14 + 3 = 17 host

### **Tổng số host sau khi dự trù cho toàn công ty:**
- Phòng Điều hành và Hành chính: 12 host
- Phòng Phát triển Sản phẩm: 23 host
- Phòng Kinh doanh và Marketing: 22 host
- Phòng Công nghệ Thông tin và Hỗ trợ: 17 host

Tổng cộng: 12 + 23 + 22 + 17 = 74 host

Tổng số host dự trù sau khi thêm 20% cho toàn bộ công ty là **74 host**.  
---
Từ đó xác định số lượng thiết bị cần thiết cho mạng của công ty IT với tổng số 52 nhân viên, cùng với giải thích lý do chọn số lượng này:

| **Thiết bị**              | **Số lượng** | **Giải thích**                                                                                                                                                   |
|---------------------------|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Router**                | 1            | Chỉ cần 1 thiết bị cho mỗi loại vì quy mô công ty vừa phải, không cần phân tách mạng phức tạp. Một router đủ để kết nối mạng nội bộ của công ty với Internet, quản lý băng thông, bảo mật cơ bản và cung cấp các dịch vụ như VPN. Không cần nhiều router vì chỉ có một kết nối chính với ISP. |
| **Switch (24-port)**      | 4            | Với 52 nhân viên và nhiều thiết bị khác (PC, server, AP), cần 4 switch để đảm bảo kết nối cho tất cả thiết bị, bao gồm dự phòng một vài cổng cho các thiết bị tương lai. |
| **Server**                | 5            | Đề xuất 5 server để phân chia rõ ràng các chức năng. Điều này giúp giảm tải và tăng hiệu suất. |
| **PC/Laptop**             | 52           | Mỗi nhân viên cần 1 máy tính (PC hoặc laptop), phù hợp với công việc và vai trò của họ trong công ty. |
| **Máy in đa chức năng**   | 4            | Mỗi phòng ban có 1 máy in để in ấn tài liệu. |
