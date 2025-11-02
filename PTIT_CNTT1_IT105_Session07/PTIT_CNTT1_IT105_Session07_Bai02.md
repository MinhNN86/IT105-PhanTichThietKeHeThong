```mermaid
graph TD

  %% ======== TẦNG 1: PRESENTATION ========
  subgraph "Presentation Tier (Giao diện người dùng)"
    A1[Web App - React/Angular]
    A2[Mobile App - Flutter/React Native]
  end

  %% ======== TẦNG 2: BUSINESS LOGIC ========
  subgraph "Business Logic Tier (Xử lý nghiệp vụ)"
    B1[Product Controller]
    B2[Supplier Controller]
    B3[Inventory Controller]
    B4[Business Services Validation, Calculation]
  end

  %% ======== TẦNG 3: DATA ACCESS ========
  subgraph "Data Access Tier (Truy cập dữ liệu)"
    C1[(Product Repository)]
    C2[(Supplier Repository)]
    C3[(Inventory Repository)]
    C4[(Database - MySQL/PostgreSQL)]
  end

  %% ======== KẾT NỐI ========
  A1 -->|REST API / HTTPS| B1
  A2 -->|REST API / HTTPS| B2

  B1 -->|Gọi service logic| B4
  B2 -->|Gọi service logic| B4
  B3 -->|Xử lý nhập - xuất kho| B4

  B1 --> C1
  B2 --> C2
  B3 --> C3

  C1 --> C4
  C2 --> C4
  C3 --> C4

```

## Mô tả chi tiết từng tầng

| Tầng               | Thành phần           | Mô tả                                                 |
| ------------------ | -------------------- | ----------------------------------------------------- |
| **Presentation**   | Web, Mobile App      | Giao diện người dùng, gửi/nhận dữ liệu qua API        |
| **Business Logic** | Controller, Service  | Xử lý quy tắc nghiệp vụ (tồn kho, nhập xuất, báo cáo) |
| **Data Access**    | Repository, Database | Lưu trữ, truy xuất và quản lý dữ liệu trong CSDL      |
