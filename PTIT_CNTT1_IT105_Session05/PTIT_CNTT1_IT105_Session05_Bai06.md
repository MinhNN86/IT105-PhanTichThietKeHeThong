```mermaid
stateDiagram-v2
    [*] --> MoiTao: Tài khoản mới được tạo

    MoiTao --> HoatDong: Xác minh tài khoản thành công
    HoatDong --> BiKhoa: Vi phạm / Bị quản trị viên khóa
    BiKhoa --> KichHoatLai: Người dùng yêu cầu kích hoạt lại
    KichHoatLai --> HoatDong: Xác nhận mở khóa thành công

    HoatDong --> [*]: Xóa tài khoản (tuỳ chọn)

```