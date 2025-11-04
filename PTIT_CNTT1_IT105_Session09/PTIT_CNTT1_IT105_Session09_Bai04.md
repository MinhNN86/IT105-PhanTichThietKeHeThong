# Bảng thuộc tính chi tiết
| **Entity**     | **Attribute** | **Kiểu dữ liệu**                       | **Vai trò / Ý nghĩa**                                    |
| -------------- | ------------- | -------------------------------------- | -------------------------------------------------------- |
| **User**       | user_id       | INT (PK)                               | Mã định danh duy nhất cho mỗi người dùng trong hệ thống. |
|                | full_name     | VARCHAR(100)                           | Họ và tên người dùng.                                    |
|                | email         | VARCHAR(100)                           | Địa chỉ email dùng để đăng nhập và nhận thông báo.       |
|                | role          | ENUM('student','instructor')           | Phân loại vai trò người dùng: học viên hoặc giảng viên.  |
|                | created_at    | DATETIME                               | Thời điểm tài khoản được tạo.                            |
| **Course**     | course_id     | INT (PK)                               | Mã định danh duy nhất cho mỗi khóa học.                  |
|                | course_name   | VARCHAR(150)                           | Tên khóa học.                                            |
|                | description   | TEXT                                   | Mô tả nội dung và mục tiêu khóa học.                     |
|                | instructor_id | INT (FK → User.user_id)                | Liên kết đến người giảng viên phụ trách khóa học.        |
|                | created_at    | DATETIME                               | Thời điểm khóa học được tạo trong hệ thống.              |
| **Enrollment** | enrollment_id | INT (PK)                               | Mã định danh duy nhất cho mỗi lượt đăng ký học.          |
|                | user_id       | INT (FK → User.user_id)                | Người dùng đã đăng ký khóa học.                          |
|                | course_id     | INT (FK → Course.course_id)            | Khóa học mà người dùng đăng ký.                          |
|                | enrolled_date | DATE                                   | Ngày người dùng đăng ký học.                             |
|                | status        | ENUM('active','completed','cancelled') | Trạng thái tham gia khóa học.                            |
