```mermaid
graph TD

%% ===== Presentation Layer =====
subgraph "Presentation Layer (Frontend)"
    A1[Web App / Mobile App]
end

%% ===== Business Logic Layer =====
subgraph "Business Logic Layer (Backend)"
    B1[Order Service]
    B2[Inventory Service]
    B3[Payment Service]
    B4[Email Service]
    B5[API Gateway / Controller]
end

%% ===== Data Layer =====
subgraph "Data Layer (Database)"
    C1[(Product DB)]
    C2[(Order DB)]
    C3[(Customer DB)]
end

%% ===== External Services =====
subgraph "External Services"
    E1[VNPay API 💳]
    E2[SMTP Mail Server 📧]
end

%% ===== Connections =====
A1 -->|REST API| B5
B5 --> B1
B1 --> B2
B1 --> B3
B3 -->|Payment Request| E1
E1 -->|Payment Response| B3
B1 --> B4
B4 -->|Send Email| E2
B1 --> C2
B2 --> C1
B1 --> C3

```

## Mô tả chi tiết các thành phần

| **Thành phần**                          | **Vai trò chính**                                                         |
| --------------------------------------- | ------------------------------------------------------------------------- |
| **Web App / Mobile App**                | Giao diện người dùng, hiển thị sản phẩm, thanh toán, xem đơn hàng.        |
| **API Gateway / Controller**            | Trung gian giữa frontend và các service backend.                          |
| **Order Service**                       | Xử lý nghiệp vụ đặt hàng, tổng tiền, cập nhật đơn hàng.                   |
| **Inventory Service**                   | Quản lý số lượng sản phẩm trong kho, cập nhật khi có giao dịch.           |
| **Payment Service**                     | Gọi đến VNPay API để xác nhận và xử lý giao dịch thanh toán.              |
| **Email Service**                       | Gửi email xác nhận cho khách hàng qua SMTP sau khi thanh toán thành công. |
| **Product DB / Order DB / Customer DB** | Lưu dữ liệu sản phẩm, đơn hàng và người dùng.                             |
| **VNPay API (External)**                | Dịch vụ thanh toán online do VNPay cung cấp.                              |
| **SMTP Mail Server (External)**         | Dịch vụ gửi email xác nhận đơn hàng.                                      |
