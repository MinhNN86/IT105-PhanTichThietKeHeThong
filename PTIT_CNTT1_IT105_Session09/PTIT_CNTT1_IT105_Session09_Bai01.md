## Các thực thể và vai trò
| **Tên thực thể**                      | **Miêu tả vai trò**                                                                                                          |
| ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Sách**                              | Chứa thông tin chi tiết của từng cuốn sách như: mã sách, tên sách, giá, mô tả, thể loại, năm xuất bản, số lượng tồn kho.     |
| **Tác giả**                           | Lưu thông tin về người viết sách, bao gồm: mã tác giả, họ tên, tiểu sử, quốc tịch. Một tác giả có thể viết nhiều sách.       |
| **Khách hàng**                        | Lưu thông tin người mua sách: mã khách hàng, họ tên, địa chỉ, số điện thoại, email. Một khách hàng có thể có nhiều đơn hàng. |
| **Đơn hàng**                          | Đại diện cho một lần mua hàng của khách, gồm: mã đơn hàng, ngày đặt, tổng tiền, trạng thái đơn hàng, mã khách hàng.          |
| **Chi tiết đơn hàng**                 | Lưu thông tin từng sản phẩm trong một đơn hàng: mã chi tiết đơn hàng, mã đơn hàng, mã sách, số lượng, đơn giá.               |
| **Nhà xuất bản** *(tuỳ chọn mở rộng)* | Quản lý thông tin về nhà xuất bản như mã NXB, tên, địa chỉ, số điện thoại, email. Mỗi sách thuộc về một nhà xuất bản.        |
