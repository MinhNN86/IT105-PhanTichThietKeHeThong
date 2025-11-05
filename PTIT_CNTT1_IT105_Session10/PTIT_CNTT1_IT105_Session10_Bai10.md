## 1. 🎯 MỤC TIÊU HỆ THỐNG

**Tên chức năng:** Quản lý khóa học cho giảng viên

**Mục tiêu:**  
Chức năng này cho phép **giảng viên** tạo, chỉnh sửa, xóa và quản lý các khóa học mà họ phụ trách trong hệ thống E-learning.  
Giúp giảng viên:
- Dễ dàng tổ chức nội dung bài giảng và học viên theo từng khóa học.
- Theo dõi tiến độ học tập của sinh viên.
- Quản lý quiz, tài liệu, bài tập, và thông tin khóa học một cách tập trung.

**Lợi ích hệ thống:**
- Tăng tính chủ động cho giảng viên trong việc giảng dạy trực tuyến.
- Cải thiện khả năng quản trị học tập (LMS).
- Giảm tải cho bộ phận quản trị hệ thống.

---

## 2. 🎭 USE CASE CHÍNH

| Thành phần | Nội dung |
|-------------|-----------|
| **Tên Use Case** | Quản lý khóa học |
| **Mô tả** | Giảng viên có thể tạo mới, cập nhật, xóa hoặc xem danh sách khóa học mà họ phụ trách. |
| **Actor** | Giảng viên |
| **Tiền điều kiện (Precondition)** | Giảng viên đã đăng nhập vào hệ thống thành công. |
| **Hậu điều kiện (Postcondition)** | Thông tin khóa học được lưu trữ hoặc cập nhật thành công trong cơ sở dữ liệu. |
| **Luồng chính (Main Flow)** | 1️⃣ Giảng viên truy cập mục “Quản lý khóa học” <br> 2️⃣ Hệ thống hiển thị danh sách khóa học hiện có. <br> 3️⃣ Giảng viên chọn **“Tạo khóa học mới”**. <br> 4️⃣ Giảng viên nhập thông tin: tên khóa học, mô tả, ngày bắt đầu, tài liệu,... <br> 5️⃣ Nhấn **Lưu** để lưu khóa học. <br> 6️⃣ Hệ thống xác nhận “Tạo khóa học thành công” và cập nhật danh sách. |
| **Luồng phụ (Alternative Flow)** | - Giảng viên chọn **“Chỉnh sửa”** một khóa học có sẵn. <br> - Cập nhật nội dung và nhấn **Lưu thay đổi**. <br> - Hệ thống hiển thị thông báo “Cập nhật thành công”. |
| **Ngoại lệ (Exception Flow)** | - Hệ thống báo lỗi khi nhập thiếu trường bắt buộc (ví dụ: tên khóa học). <br> - Nếu mất kết nối khi lưu, hiển thị “Không thể lưu, vui lòng thử lại.” |

---

## 3. 🖥️ GIAO DIỆN NGƯỜI DÙNG 


---

## 4. 🗄️ DỮ LIỆU LIÊN QUAN

### **Bảng 1: Course**
| Tên cột | Kiểu dữ liệu | Ghi chú |
|----------|---------------|--------|
| `course_id` | INT (PK) | Mã khóa học |
| `teacher_id` | INT (FK) | Mã giảng viên |
| `course_name` | VARCHAR(255) | Tên khóa học |
| `description` | TEXT | Mô tả nội dung khóa học |
| `start_date` | DATE | Ngày bắt đầu |
| `end_date` | DATE | Ngày kết thúc |
| `status` | ENUM('Active','Inactive','Ended') | Trạng thái khóa học |
| `created_at` | DATETIME | Ngày tạo |
| `updated_at` | DATETIME | Ngày cập nhật |

### **Bảng 2: Course_Material**
| Tên cột | Kiểu dữ liệu | Ghi chú |
|----------|--------------|--------|
| `material_id` | INT (PK) | Mã tài liệu |
| `course_id` | INT (FK) | Khóa học liên kết |
| `file_name` | VARCHAR(255) | Tên file |
| `file_url` | VARCHAR(255) | Đường dẫn lưu trữ |
| `upload_date` | DATETIME | Ngày tải lên |

---

## 5. ⚙️ YÊU CẦU PHI CHỨC NĂNG (NFR)

| Mã | Yêu cầu phi chức năng | Cách kiểm thử |
|----|------------------------|----------------|
| **NFR-01** | Thời gian tải danh sách khóa học không vượt quá **3 giây** khi có dưới 100 khóa học. | Dùng công cụ đo hiệu năng (Lighthouse / JMeter). |
| **NFR-02** | Hệ thống chỉ cho phép **giảng viên có quyền hợp lệ** truy cập và chỉnh sửa khóa học của họ. | Thử đăng nhập bằng tài khoản khác → Không thể truy cập chức năng. |
| **NFR-03** | Giao diện phải **tương thích trên thiết bị di động (responsive)**. | Kiểm thử trên trình duyệt Chrome devtools ở các kích thước khác nhau. |

---