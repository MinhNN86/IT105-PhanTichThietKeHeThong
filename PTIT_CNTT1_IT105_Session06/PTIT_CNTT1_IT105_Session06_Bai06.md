## Sơ đồ Use Case
```mermaid
graph TD
%% Định nghĩa các actor
    A[Người dùng]:::actor
    B[Quản trị viên]:::actor

%% Các Use Case
    UC1((Đăng ký tài khoản))
    UC2((Tìm kiếm sách))
    UC3((Mượn sách))
    UC4((Trả sách))
    UC5((Quản lý sách))
    UC6((Thêm sách))
    UC7((Sửa thông tin sách))
    UC8((Xóa sách))

%% Kết nối actor và use case
    A --> UC1
    A --> UC2
    A --> UC3
    A --> UC4

    B --> UC5
    UC5 --> UC6
    UC5 --> UC7
    UC5 --> UC8

```
## Sơ đồ Class Diagram
```mermaid
classDiagram
    class NguoiDung {
        - maNguoiDung : String
        - hoTen : String
        - email : String
        - matKhau : String
        + dangKyTaiKhoan()
        + timKiemSach()
        + muonSach()
        + traSach()
    }

    class Admin {
        - maAdmin : String
        - hoTen : String
        + themSach()
        + suaSach()
        + xoaSach()
    }

    class Sach {
        - maSach : String
        - tenSach : String
        - tacGia : String
        - theLoai : String
        - trangThai : String
        + hienThiThongTin()
    }

    class MuonSach {
        - maPhieu : String
        - ngayMuon : Date
        - ngayTraDuKien : Date
        - ngayTraThucTe : Date
        + taoPhieuMuon()
        + capNhatTrangThaiTra()
    }

    class ThuVien {
        - tenThuVien : String
        - diaChi : String
        + timKiemSach()
    }

    %% Mối quan hệ
    NguoiDung "1" -- "0..*" MuonSach 
    MuonSach "1" -- "1" Sach
    Admin "1" -- "0..*" Sach
    ThuVien "1" -- "0..*" Sach 
```

## Giải thích logic chuyển đổi

| **Bước**                          | **Mô tả**                                                                               | **Kết quả**                                         |
| --------------------------------- |-----------------------------------------------------------------------------------------| --------------------------------------------------- |
| **Xác định actor**                | Dựa vào Use Case Diagram, có 2 actor: *Người dùng*, *Admin*                             | Sinh ra 2 class: `NguoiDung`, `Admin`               |
| **Xác định Use Case chính**   | Từ các hành động (Đăng ký, Mượn, Trả...)                                                | Sinh ra các phương thức tương ứng trong `NguoiDung` |
| **Xác định thực thể (entity)** | Các đối tượng có dữ liệu riêng như `Sach`, `MuonSach`, `ThuVien`                        | Mỗi entity trở thành một class                      |
| **Xác định quan hệ giữa các lớp** | - `NguoiDung` mượn nhiều `Sach` qua `MuonSach`<br>- `Admin` quản lý nhiều `Sach`   | Xây dựng các association (1–N)                      |
|**Gắn Multiplicity**          | Dựa vào hành vi: 1 người dùng → nhiều phiếu mượn, 1 phiếu mượn → 1 sách                 | Bổ sung “1..*”, “1”, “0..*” vào sơ đồ               |
