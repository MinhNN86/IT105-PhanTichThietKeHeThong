## Use Case Diagram – Hệ thống quản lý sinh viên

```mermaid
graph TD
    A[Người dùng / Quản trị viên] --> UC1(Thêm sinh viên)
    A --> UC2(Sửa thông tin sinh viên)
    A --> UC3(Xóa sinh viên)
    A --> UC4(Xem danh sách sinh viên)

    subgraph "Hệ thống Quản lý Sinh viên"
        UC1
        UC2
        UC3
        UC4
    end

```

## Class Diagram – Các lớp trong hệ thống

```mermaid
classDiagram
    class SinhVien {
        -maSV: String
        -hoTen: String
        -ngaySinh: Date
        -lop: String
        -email: String
        +getThongTin(): String
    }

    class GiaoVien {
        -maGV: String
        -hoTen: String
        -boMon: String
        +quanLySinhVien(): void
    }

    class HeThongQuanLy {
        +themSinhVien(sv: SinhVien): void
        +suaSinhVien(maSV: String): void
        +xoaSinhVien(maSV: String): void
        +xemDanhSach(): List~SinhVien~
    }

    class Database {
        +luuDuLieu(sv: SinhVien): void
        +capNhatDuLieu(sv: SinhVien): void
        +xoaDuLieu(maSV: String): void
        +layDanhSach(): List~SinhVien~
    }

    GiaoVien --> HeThongQuanLy : "sử dụng"
    HeThongQuanLy --> SinhVien : "quản lý"
    HeThongQuanLy --> Database : "giao tiếp với"

```

## Sequence Diagram – Quy trình “Thêm sinh viên”

```mermaid
sequenceDiagram
    actor GiaoVien as "Người dùng"
    participant HeThong as "Hệ thống Quản lý"
    participant Database as "Cơ sở dữ liệu"

    GiaoVien->>HeThong: Nhập thông tin sinh viên mới
    HeThong->>Database: Gửi yêu cầu lưu thông tin (INSERT)
    Database-->>HeThong: Trả kết quả (Thành công / Thất bại)
    HeThong-->>GiaoVien: Hiển thị thông báo kết quả thêm sinh viên

```

# Mối liên hệ giữa 3 sơ đồ

| Sơ đồ                | Mục đích                                                | Liên kết                                                                 |
| -------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Use Case Diagram** | Xác định chức năng chính mà người dùng có thể thực hiện | Use Case “Thêm sinh viên” được chọn để mô tả chi tiết                    |
| **Class Diagram**    | Mô tả cấu trúc các lớp và quan hệ giữa chúng            | Các lớp `SinhVien`, `HeThongQuanLy`, `Database` được dùng trong Sequence |
| **Sequence Diagram** | Thể hiện luồng tương tác cụ thể theo thời gian          | Minh họa chi tiết quá trình từ Use Case → hành vi của các lớp            |
