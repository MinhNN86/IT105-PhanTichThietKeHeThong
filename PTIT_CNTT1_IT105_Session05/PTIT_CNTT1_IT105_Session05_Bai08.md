```mermaid
stateDiagram-v2
    [*] --> ChoNhapKho: Sản phẩm được đặt hàng
    
    ChoNhapKho: Chờ Nhập Kho
    ConHang: Còn Hàng
    HetHang: Hết hàng
    NgungKinhDoanh: Ngừng kinh doanh
    
    ChoNhapKho --> ConHang: Nhập kho thành công
    ConHang --> HetHang: Bán hết sản phẩm
    HetHang --> ConHang: Nhập thêm hàng mới
    ConHang --> NgungKinhDoanh: Ngừng bán
    HetHang --> NgungKinhDoanh: Ngừng bán
    
    NgungKinhDoanh --> [*]: Kết thúc vòng đời sản phẩm
    
```

## Logic chuyển trạng thái
| Từ trạng thái       | Đến trạng thái   | Sự kiện kích hoạt (Trigger/Event)         |
| ------------------- | ---------------- | ----------------------------------------- |
| Chờ nhập kho        | Còn hàng         | **Nhập kho thành công**                   |
| Còn hàng            | Hết hàng         | **Bán hết sản phẩm**                      |
| Hết hàng            | Còn hàng         | **Nhập thêm hàng mới**                    |
| Còn hàng / Hết hàng | Ngừng kinh doanh | **Quản lý quyết định ngừng bán sản phẩm** |
