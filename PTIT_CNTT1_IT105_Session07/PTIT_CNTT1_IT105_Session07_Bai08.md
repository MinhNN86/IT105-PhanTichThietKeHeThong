```mermaid
graph TB
    %% ======= Presentation Layer =======
    subgraph Presentation["🖥️ Presentation Layer"]
        A1[ProductView]
        A2[OrderView]
        A3[LoginView]
        A4[ReportView]
    end

    %% ======= Business Logic Layer =======
    subgraph Business["⚙️ Business Logic Layer"]
        B1[ProductService]
        B2[OrderService]
        B3[UserService]
        B4[ReportService]
    end

    %% ======= Data Access Layer =======
    subgraph Data["💾 Data Access Layer"]
        C1[ProductRepository]
        C2[OrderRepository]
        C3[UserRepository]
        C4[ReportRepository]
        DB[(Database)]
    end

    %% ======= Connections =======
    %% Presentation -> Business
    A1 --> B1
    A2 --> B2
    A3 --> B3
    A4 --> B4

    %% Business -> Data
    B1 --> C1
    B2 --> C2
    B3 --> C3
    B4 --> C4

    %% Data -> Database
    C1 --> DB
    C2 --> DB
    C3 --> DB
    C4 --> DB

```

## Mô tả kiến trúc từng lớp
| **Tầng**                                  | **Vai trò**                                                                          | **Các thành phần (Modules / Classes)**                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| **Presentation Layer (Tầng trình bày)**   | Giao diện người dùng (Web hoặc Mobile). Gửi yêu cầu đến backend và hiển thị dữ liệu. | - `ProductView`<br>- `OrderView`<br>- `LoginView`<br>- `ReportView`                        |
| **Business Logic Layer (Tầng nghiệp vụ)** | Xử lý các nghiệp vụ như kiểm tra tính hợp lệ, tính toán doanh thu, xử lý đơn hàng.   | - `ProductService`<br>- `OrderService`<br>- `UserService`<br>- `ReportService`             |
| **Data Access Layer (Tầng dữ liệu)**      | Giao tiếp trực tiếp với cơ sở dữ liệu, thực hiện CRUD.                               | - `ProductRepository`<br>- `OrderRepository`<br>- `UserRepository`<br>- `ReportRepository` |
