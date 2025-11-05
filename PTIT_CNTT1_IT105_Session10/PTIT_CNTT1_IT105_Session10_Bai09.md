## 1. USE CASE

| Mục | Nội dung |
|------|-----------|
| **Tên Use Case** | Làm bài Quiz trực tuyến |
| **Mô tả** | Người dùng truy cập vào hệ thống, chọn bài quiz, trả lời các câu hỏi trong thời gian quy định, nộp bài và xem kết quả. |
| **Actor** | Người học (User) |
| **Tiền điều kiện (Precondition)** | Người dùng đã đăng nhập và được cấp quyền truy cập quiz. |
| **Hậu điều kiện (Postcondition)** | Kết quả bài làm được lưu vào hệ thống và hiển thị cho người dùng. |
| **Luồng chính (Main Flow)** | 1. Người dùng đăng nhập hệ thống.<br>2. Chọn mục “Quiz”.<br>3. Chọn bài quiz cụ thể.<br>4. Hệ thống hiển thị danh sách câu hỏi và bộ đếm thời gian.<br>5. Người dùng lần lượt chọn đáp án cho từng câu.<br>6. Sau khi hoàn thành, người dùng nhấn “Nộp bài”.<br>7. Hệ thống chấm điểm tự động và hiển thị kết quả ngay. |
| **Luồng phụ (Alternative Flow)** | - Nếu người dùng hết thời gian, hệ thống tự động nộp bài.<br>- Nếu người dùng thoát giữa chừng, hệ thống lưu tạm tiến độ. |
| **Ngoại lệ (Exception Flow)** | - Kết nối mạng bị gián đoạn → Hệ thống hiển thị thông báo “Mất kết nối” và lưu tiến độ hiện tại.<br>- Server lỗi → Hiển thị thông báo “Không thể nộp bài, vui lòng thử lại sau.” |

---

## 2. YÊU CẦU CHỨC NĂNG (Functional Requirements)

| Mã | Yêu cầu | Mô tả |
|------|----------|--------|
| **FR-01** | Người dùng có thể xem danh sách các bài quiz có sẵn. | Hệ thống hiển thị danh sách quiz gồm tên, mô tả, số câu hỏi, và thời gian làm bài. |
| **FR-02** | Người dùng có thể bắt đầu làm bài quiz. | Khi người dùng chọn “Bắt đầu”, hệ thống hiển thị câu hỏi đầu tiên và bộ đếm thời gian. |
| **FR-03** | Hệ thống hiển thị câu hỏi và 4 lựa chọn đáp án. | Mỗi câu hỏi có thể chỉ có 1 đáp án đúng. |
| **FR-04** | Người dùng có thể chuyển qua lại giữa các câu hỏi. | Có nút “Next” và “Previous” để điều hướng câu hỏi. |
| **FR-05** | Người dùng có thể nộp bài trước khi hết giờ. | Khi nhấn “Nộp bài”, hệ thống yêu cầu xác nhận và chấm điểm. |
| **FR-06** | Hệ thống tự động nộp bài khi hết thời gian. | Đảm bảo bài được chấm ngay cả khi người dùng không nhấn nộp. |
| **FR-07** | Hệ thống hiển thị kết quả sau khi nộp. | Hiển thị điểm số, số câu đúng/sai, và link “Xem chi tiết kết quả”. |
| **FR-08** | Hệ thống lưu kết quả vào cơ sở dữ liệu. | Bao gồm: ID người dùng, ID quiz, điểm số, thời gian làm, ngày làm. |
| **FR-09** | Người dùng có thể xem lại bài đã làm. | Hiển thị lại câu hỏi, đáp án đã chọn, đáp án đúng, và lời giải (nếu có). |

---

## 3. YÊU CẦU PHI CHỨC NĂNG (Non-Functional Requirements)

| Mã | Loại | Mô tả |
|------|------|--------|
| **NFR-01** | Hiệu năng | Hệ thống phải tải trang quiz trong ≤ 2 giây và phản hồi khi nộp bài trong ≤ 3 giây. |
| **NFR-02** | Bảo mật | Mỗi người dùng chỉ được phép làm quiz của chính mình. Dữ liệu điểm và đáp án được mã hóa. |
| **NFR-03** | Khả năng mở rộng | Hệ thống có thể phục vụ tối thiểu 10.000 người dùng làm quiz đồng thời mà không lỗi. |
| **NFR-04** | Trải nghiệm người dùng | Giao diện phải rõ ràng, dễ thao tác trên cả máy tính và thiết bị di động. |
| **NFR-05** | Độ tin cậy | Hệ thống lưu tạm bài làm mỗi 30 giây để tránh mất dữ liệu khi mất kết nối. |

---