## Danh sách Stakeholders
| **Stakeholder**                          | **Vai trò**                                              | **Nguồn yêu cầu**                                                 |
| ---------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------- |
| **Học viên (Student)**                   | Người dùng chính, đăng ký, học và làm bài kiểm tra       | Mong muốn học mọi lúc, mọi nơi; cần giao diện thân thiện, dễ dùng |
| **Giảng viên (Instructor)**              | Cung cấp khóa học, quản lý nội dung bài giảng, chấm điểm | Muốn có công cụ dễ tải bài giảng, giao bài, theo dõi học viên     |
| **Quản trị viên (Admin)**                | Quản lý người dùng, khóa học, báo cáo hệ thống           | Yêu cầu quyền quản trị, bảo mật và theo dõi toàn hệ thống         |
| **Bộ phận kỹ thuật (IT Support)**        | Duy trì hệ thống, xử lý lỗi kỹ thuật                     | Yêu cầu về hiệu suất, khả năng mở rộng và bảo trì                 |
| **Đối tác thanh toán (Payment Gateway)** | Cung cấp dịch vụ thanh toán trực tuyến (VD: Momo, VNPay) | Yêu cầu tích hợp API an toàn, xác nhận giao dịch nhanh            |
| **Bộ phận marketing**                    | Quảng bá khóa học, thu hút người dùng                    | Cần dữ liệu học viên, thống kê khóa học nổi bật                   |
| **Cơ quan kiểm định (Accreditation)**    | Đánh giá chất lượng đào tạo                              | Cần truy cập báo cáo học tập và đánh giá hệ thống                 |

## Yêu cầu chức năng
| **Mã FR** | **Yêu cầu chức năng**           | **Mô tả**                                                      |
| --------- | ------------------------------- | -------------------------------------------------------------- |
| **FR01**  | Đăng ký và đăng nhập            | Người dùng tạo tài khoản hoặc đăng nhập qua email, mạng xã hội |
| **FR02**  | Duyệt và tìm kiếm khóa học      | Học viên xem danh sách khóa học, lọc theo chủ đề, giảng viên   |
| **FR03**  | Ghi danh khóa học               | Học viên đăng ký tham gia khóa học                             |
| **FR04**  | Thanh toán online               | Học viên thanh toán qua VNPay, Momo                            |
| **FR05**  | Xem và học bài                  | Học viên truy cập nội dung bài học (video, PDF, quiz)          |
| **FR06**  | Làm bài kiểm tra và nộp bài     | Học viên thực hiện bài test trắc nghiệm hoặc bài tập           |
| **FR07**  | Theo dõi tiến độ học tập        | Hệ thống lưu tiến độ và hiển thị % hoàn thành khóa học         |
| **FR08**  | Giảng viên quản lý nội dung     | Giảng viên tạo, cập nhật và xóa bài học                        |
| **FR09**  | Giảng viên chấm bài và phản hồi | Giảng viên xem kết quả, gửi nhận xét cho học viên              |
| **FR10**  | Admin quản lý hệ thống          | Quản trị viên thêm, xóa, khóa tài khoản, xem báo cáo hệ thống  |
| **FR11**  | Báo cáo doanh thu               | Hệ thống thống kê doanh thu và số lượng học viên               |

## Yêu cầu phi chức năng
| **Loại yêu cầu**                       | **Mô tả**                                                                     |
| -------------------------------------- | ----------------------------------------------------------------------------- |
| **Hiệu năng (Performance)**            | Hệ thống tải trang < 2 giây, chịu được > 1000 người dùng đồng thời            |
| **Bảo mật (Security)**                 | Mã hóa mật khẩu, xác thực 2 lớp, chống SQL Injection, phân quyền rõ ràng      |
| **Khả năng mở rộng (Scalability)**     | Có thể thêm nhiều khóa học, học viên, giảng viên mà không ảnh hưởng hiệu năng |
| **Tính sẵn sàng (Availability)**       | Hệ thống hoạt động 99,5% thời gian, có backup dữ liệu định kỳ                 |
| **Dễ sử dụng (Usability)**             | Giao diện thân thiện, đa ngôn ngữ, có hướng dẫn cho người mới                 |
| **Khả năng tích hợp (Integration)**    | Hỗ trợ API kết nối với hệ thống thanh toán, LMS khác                          |
| **Khả năng bảo trì (Maintainability)** | Cấu trúc code module, dễ cập nhật và sửa lỗi                                  |
