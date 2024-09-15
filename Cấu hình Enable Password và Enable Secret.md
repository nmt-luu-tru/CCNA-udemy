Dưới đây là lý thuyết chi tiết và các ví dụ cụ thể về **Enable Password** và **Enable Secret** trên router hoặc switch, kèm theo kết quả khi thực hiện cấu hình:

### **Enable Password**

**Mục đích:**
- `Enable Password` được sử dụng để bảo vệ quyền truy cập vào chế độ EXEC cao cấp (privileged EXEC mode) của router hoặc switch.

**Đặc điểm:**
- Mật khẩu này có thể được hiển thị dưới dạng văn bản thuần túy trong cấu hình, dễ dàng bị đọc nếu không được mã hóa.
- Sử dụng lệnh `service password-encryption` để mã hóa đơn giản mật khẩu này, nhưng mức độ bảo mật vẫn không cao bằng `Enable Secret`.

**Ví dụ cấu hình Enable Password:**

1. **Cấu hình Enable Password:**
   ```shell
   Router> enable
   Router# configure terminal
   Router(config)# enable password myEnablePassword
   Router(config)# exit
   ```
   
2. **Mã hóa mật khẩu với `service password-encryption`:**
   ```shell
   Router# configure terminal
   Router(config)# service password-encryption
   Router(config)# exit
   ```
   
3. **Kết quả kiểm tra trong cấu hình:**
   - Sau khi cấu hình xong, sử dụng lệnh `show running-config` để kiểm tra:
   ```shell
   Router# show running-config
   !
   enable password 7 0822455D0A16
   !
   ```
   - Nếu không sử dụng `service password-encryption`, mật khẩu sẽ hiển thị dưới dạng thuần túy:
   ```shell
   enable password myEnablePassword
   ```

### **Enable Secret**

**Mục đích:**
- `Enable Secret` cũng dùng để bảo vệ quyền truy cập vào chế độ EXEC cao cấp, nhưng an toàn hơn nhiều so với `Enable Password`.

**Đặc điểm:**
- Mật khẩu được mã hóa bằng thuật toán MD5 và không thể giải mã ngược lại thành văn bản thuần túy.
- Đảm bảo bảo mật cao hơn và là phương pháp ưu tiên khi bảo vệ truy cập EXEC cao cấp.
- Nếu cả `Enable Password` và `Enable Secret` đều được cấu hình, `Enable Secret` sẽ được ưu tiên sử dụng.

**Ví dụ cấu hình Enable Secret:**

1. **Cấu hình Enable Secret:**
   ```shell
   Router> enable
   Router# configure terminal
   Router(config)# enable secret mySecureSecret
   Router(config)# exit
   ```
   
2. **Kết quả kiểm tra trong cấu hình:**
   - Kiểm tra cấu hình sau khi thiết lập bằng lệnh `show running-config`:
   ```shell
   Router# show running-config
   !
   enable secret 5 $1$mERr$H9TSOZOWsXmIRtM2Rlmfb1
   !
   ```
   - Mật khẩu `Enable Secret` luôn hiển thị dưới dạng mã băm MD5, giúp bảo mật thông tin đăng nhập.

### **So sánh và Ưu tiên:**

- **Ưu tiên của `Enable Secret`**:
  - Nếu bạn đã cấu hình cả `Enable Password` và `Enable Secret`, khi nhập lệnh `enable`, thiết bị sẽ yêu cầu nhập mật khẩu `Enable Secret`, vì nó an toàn hơn và được ưu tiên.
  
- **Ví dụ về cấu hình cả hai loại mật khẩu:**
   ```shell
   Router(config)# enable password myEnablePassword
   Router(config)# enable secret mySecureSecret
   ```
   
- **Kết quả kiểm tra với cả hai loại mật khẩu:**
   - Khi bạn gõ lệnh `enable` từ chế độ người dùng EXEC, bạn sẽ được yêu cầu nhập mật khẩu của `Enable Secret` chứ không phải `Enable Password`:
   ```shell
   Router> enable
   Password: 
   ```
   
   - **Nếu nhập mật khẩu `Enable Secret` (`mySecureSecret`), bạn sẽ được cấp quyền vào chế độ EXEC cao cấp.**

### **Tại sao nên sử dụng Enable Secret thay vì Enable Password?**
- **Bảo mật hơn**: `Enable Secret` sử dụng mã hóa MD5 mạnh mẽ, không thể giải mã ngược, trong khi `Enable Password` có thể được mã hóa đơn giản nhưng vẫn có thể bị giải mã.
- **Tiêu chuẩn bảo mật**: `Enable Secret` là lựa chọn tiêu chuẩn trong hầu hết các môi trường sản xuất và mạng doanh nghiệp.

**Tóm lại**, khi bảo mật thiết bị mạng, `Enable Secret` luôn là lựa chọn ưu tiên vì nó cung cấp mức độ bảo mật cao hơn `Enable Password`. Bạn nên sử dụng `Enable Secret` để bảo vệ quyền truy cập vào chế độ EXEC cao cấp, và chỉ sử dụng `Enable Password` nếu cần thiết và trong các môi trường không yêu cầu bảo mật cao.
