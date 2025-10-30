```mermaid
graph TD
    A[Khách hàng] --> UC1((Đặt chỗ))
    A --> UC2((Chọn ghế))
    A --> UC3((Thanh toán))
    A --> UC4((Hủy vé))
    A --> UC5((Xem lịch chiếu))

    B[Hệ thống thanh toán] --> UC3
    C[Quản trị viên] --> UC6((Quản lý lịch chiếu))

    UC1 -->|include| UC2
    UC2 -->|include| UC3
    UC3 -->|extend| UC4

```

## Các Use Case chính
| Tên Use Case           | Mô tả ngắn gọn                                         | Actor liên quan                 |
| ---------------------- | ------------------------------------------------------ | ------------------------------- |
| **Đặt chỗ**            | Khách hàng chọn phim, ngày chiếu, giờ chiếu            | Khách hàng                      |
| **Chọn ghế**           | Hiển thị sơ đồ ghế để người dùng chọn vị trí mong muốn | Khách hàng                      |
| **Thanh toán**         | Thanh toán online (VNPay, Momo, COD...)                | Khách hàng, Hệ thống thanh toán |
| **Hủy vé**             | Khách hàng có thể hủy vé trong thời gian cho phép      | Khách hàng                      |
| **Xem lịch chiếu**     | Xem danh sách phim, suất chiếu                         | Khách hàng                      |
| **Quản lý lịch chiếu** | Cập nhật phim, giờ chiếu, rạp                          | Quản trị viên                   |


