## Phần A – Giao diện người dùng
![Ảnh giao diện gốc](Ex02.png)

## Phần B – Thiết kế bảng cơ sở dữ liệu
## 1. Bảng `users`
| Tên cột | Kiểu dữ liệu | Mô tả | Ghi chú |
|----------|--------------|-------|---------|
| user_id | INT | Mã người dùng | **PK**, AUTO_INCREMENT |
| full_name | VARCHAR(100) | Họ và tên | NOT NULL |
| email | VARCHAR(150) | Email đăng nhập | UNIQUE, NOT NULL |
| password | VARCHAR(255) | Mật khẩu đã mã hóa | NOT NULL |
| created_at | DATETIME | Ngày tạo tài khoản | DEFAULT CURRENT_TIMESTAMP |

---

## 2. Bảng `courses`
| Tên cột | Kiểu dữ liệu | Mô tả | Ghi chú |
|----------|--------------|-------|---------|
| course_id | INT | Mã khóa học | **PK**, AUTO_INCREMENT |
| course_name | VARCHAR(150) | Tên khóa học | NOT NULL |
| description | TEXT | Mô tả chi tiết khóa học |  |
| price | DECIMAL(10,2) | Học phí |  |
| duration | INT | Số giờ học |  |
| created_at | DATETIME | Ngày tạo | DEFAULT CURRENT_TIMESTAMP |

---

## 3. Bảng `enrollments`
| Tên cột | Kiểu dữ liệu | Mô tả | Ghi chú |
|----------|--------------|-------|---------|
| enrollment_id | INT | Mã đăng ký | **PK**, AUTO_INCREMENT |
| user_id | INT | Mã người dùng đăng ký | **FK** → users.user_id |
| course_id | INT | Mã khóa học đăng ký | **FK** → courses.course_id |
| payment_method | VARCHAR(50) | Phương thức thanh toán (VNPay, Momo, Bank) |  |
| payment_status | ENUM('pending','paid','failed') | Trạng thái thanh toán | DEFAULT 'pending' |
| enrolled_at | DATETIME | Ngày đăng ký | DEFAULT CURRENT_TIMESTAMP |

---