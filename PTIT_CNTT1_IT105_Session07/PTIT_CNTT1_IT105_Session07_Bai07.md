```mermaid
graph TB
    %% ======= Tầng Giao diện (Frontend) =======
    subgraph Frontend["🎨 Frontend Layer"]
        A1[Course Management UI]
        A2[Quiz Management UI]
        A3[Result Display UI]
    end

    %% ======= Tầng Xử lý nghiệp vụ (Backend) =======
    subgraph Backend["⚙️ Backend Layer"]
        B1[User Management Module]
        B2[Authentication Module]
        B3[Course Management Module]
        B4[Quiz Management Module]
        B5[Result Management Module]
    end

    %% ======= Tầng CSDL (Database) =======
    subgraph Database["🗄️ Database Layer"]
        D1[(User Table)]
        D2[(Course Table)]
        D3[(Quiz Table)]
        D4[(Result Table)]
    end

    %% ======= Kết nối giữa các tầng =======
    A1 --> B3
    A2 --> B4
    A3 --> B5
    B1 --> D1
    B2 --> D1
    B3 --> D2
    B4 --> D3
    B5 --> D4

```
## Bảng Mapping Use Case → Module
| **Use Case**      | **Module tương ứng** | **Tầng kiến trúc**      | **Mô tả chức năng chính**                                |
| ----------------- | -------------------- | ----------------------- | -------------------------------------------------------- |
| Đăng ký tài khoản | User Management      | Backend, Database       | Quản lý thông tin người dùng, lưu dữ liệu người dùng mới |
| Đăng nhập         | Authentication       | Backend                 | Xác thực thông tin người dùng, tạo session/token         |
| Xem khóa học      | Course Management    | Frontend + Backend      | Hiển thị danh sách khóa học, lấy dữ liệu từ DB           |
| Làm bài quiz      | Quiz Management      | Frontend + Backend      | Giao diện làm quiz, tính điểm tạm thời                   |
| Xem kết quả       | Result Management    | Frontend + Backend + DB | Hiển thị kết quả, lưu lịch sử làm bài và điểm số         |
