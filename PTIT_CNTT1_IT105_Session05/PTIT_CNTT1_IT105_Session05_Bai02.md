```mermaid
sequenceDiagram
    participant Customer as Khách hàng
    participant Website as Website
    participant AuthSystem as Hệ thống xác minh

    %% Synchronous messages
    Customer->>Website: Nhập tài khoản + mật khẩu (Yêu cầu đăng nhập)
    Website->>AuthSystem: Gửi thông tin đăng nhập để xác minh

    %% Return messages
    AuthSystem-->>Website: Kết quả xác minh (Hợp lệ/Không hợp lệ)
    Website-->>Customer: Trả về giao diện cá nhân (nếu hợp lệ)

```

## Phân loại thông điệp
| Loại thông điệp          | Mô tả                                               | Ví dụ trong sơ đồ                                                                           |
| ------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Synchronous Message**  | Bắt buộc chờ phản hồi trước khi tiếp tục.           | Khách hàng → Website (đăng nhập) <br> Website → Hệ thống xác minh                           |
| **Asynchronous Message** | Không cần chờ phản hồi, có thể thực hiện việc khác. | (Không có trong ví dụ này, vì login thường chờ phản hồi)                                    |
| **Return Message**       | Thông điệp phản hồi từ đối tượng nhận.              | Hệ thống xác minh → Website (trả kết quả) <br> Website → Khách hàng (trả giao diện cá nhân) |
