## 🏫 HỆ THỐNG HỌC TRỰC TUYẾN (E-LEARNING SYSTEM)

### 1. Hiệu năng (Performance)
- **Mô tả:** Hệ thống phải xử lý và tải trang trong **≤ 2 giây** cho các thao tác như xem bài học, làm quiz, hoặc nộp bài tập.
- **Tiêu chí kiểm thử:** Dùng công cụ Lighthouse hoặc JMeter để đo thời gian phản hồi trung bình khi có 1000 người dùng truy cập đồng thời.
- **Kỳ vọng:** Thời gian phản hồi trung bình ≤ 2 giây.

---

### 2. Tính sẵn sàng (Availability)
- **Mô tả:** Hệ thống học trực tuyến phải duy trì mức **sẵn sàng hoạt động 99.5%** mỗi tháng.
- **Tiêu chí kiểm thử:** Theo dõi uptime qua công cụ giám sát (như UptimeRobot hoặc AWS CloudWatch).
- **Kỳ vọng:** Thời gian downtime không vượt quá **3,6 giờ/tháng**.

---

### 3. Bảo mật (Security)
- **Mô tả:** Tất cả mật khẩu người dùng phải được lưu trữ bằng thuật toán **bcrypt** với ít nhất **10 vòng mã hóa (salt rounds)**.
- **Tiêu chí kiểm thử:** Kiểm tra mã nguồn hoặc cơ sở dữ liệu đảm bảo không có mật khẩu dạng plain text.
- **Kỳ vọng:** 100% mật khẩu được mã hóa trước khi lưu trữ.

---

## 🛒 HỆ THỐNG BÁN HÀNG THƯƠNG MẠI ĐIỆN TỬ (E-COMMERCE SYSTEM)

### 1. Hiệu năng (Performance)
- **Mô tả:** Trang danh mục sản phẩm phải hiển thị **ít nhất 50 sản phẩm trong ≤ 1.5 giây**.
- **Tiêu chí kiểm thử:** Dùng Postman hoặc JMeter để đo thời gian phản hồi API `/products`.
- **Kỳ vọng:** 95% các lần tải trang có thời gian phản hồi ≤ 1.5 giây.

---

### 2. Bảo mật (Security)
- **Mô tả:** Hệ thống thanh toán phải tuân thủ tiêu chuẩn **PCI DSS**, đảm bảo mã hóa dữ liệu thẻ thanh toán bằng **SSL/TLS 1.3**.
- **Tiêu chí kiểm thử:** Kiểm tra chứng chỉ SSL và xác nhận dữ liệu thẻ không được log hoặc lưu trữ không mã hóa.
- **Kỳ vọng:** 100% giao dịch diễn ra qua kết nối HTTPS bảo mật.

---

### 3. Khả năng mở rộng (Scalability)
- **Mô tả:** Hệ thống phải có khả năng mở rộng để hỗ trợ **tối thiểu 10.000 người dùng đồng thời** mà không giảm hiệu năng quá 20%.
- **Tiêu chí kiểm thử:** Kiểm tra bằng stress test trên AWS/GCP, đo thời gian phản hồi và tỷ lệ lỗi khi tăng tải dần.
- **Kỳ vọng:** Hệ thống vẫn hoạt động ổn định, CPU sử dụng ≤ 80%.

---