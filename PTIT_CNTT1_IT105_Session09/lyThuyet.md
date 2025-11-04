# Lesson1: Tổng Quan Về ERD và So Sánh Với Class Diagram

## 🧩 Khái Niệm Về ERD (Entity Relationship Diagram)

**Định nghĩa:**  
ERD là sơ đồ thể hiện cấu trúc dữ liệu của hệ thống, mô tả các **thực thể (Entity)**, **thuộc tính (Attribute)** và **mối quan hệ (Relationship)** giữa các thực thể.

### 🎯 Mục Đích Của ERD
- Là bước đầu trong **thiết kế cơ sở dữ liệu**.
- Giúp **phân tích mối quan hệ dữ liệu** trước khi triển khai.
- Hỗ trợ giao tiếp giữa **phân tích viên và nhà phát triển**.
- Đảm bảo **cấu trúc dữ liệu hợp lý**, tránh trùng lặp.

### 🔑 Thành Phần Chính
| Thành phần | Ý nghĩa | Ví dụ |
|-------------|----------|-------|
| Entity | Đối tượng dữ liệu | Student, Course |
| Attribute | Đặc điểm của đối tượng | Name, Email |
| Primary Key | Khóa định danh duy nhất | StudentID |
| Foreign Key | Liên kết đến bảng khác | CourseID |
| Relationship | Mối quan hệ giữa các bảng | Student - Enrolls - Course |
| Cardinality | Bội số (1:1, 1:N, N:M) | 1 sinh viên học nhiều môn |

### 🔗 Các Loại Quan Hệ
- **1:1** – Mỗi thực thể A liên kết với duy nhất 1 thực thể B.
- **1:N** – Một thực thể A liên kết với nhiều thực thể B.
- **N:N** – Hai thực thể liên kết nhiều – nhiều (thường tách ra bảng trung gian).

### 🧠 Ví Dụ Minh Họa
**Hệ thống quản lý khóa học:**
- Entity: `Student`, `Course`, `Enrollment`
- Relationship: `Student` đăng ký `Course` (N:N thông qua `Enrollment`)

---

## 🧱 Class Diagram (Sơ Đồ Lớp)

**Định nghĩa:**  
Là sơ đồ trong UML mô tả **các lớp (Class)**, **thuộc tính (Attributes)**, **phương thức (Methods)** và **quan hệ** giữa chúng.

### 🎯 Mục Đích
- Phân tích & thiết kế **hệ thống hướng đối tượng (OOP)**.
- Giúp lập trình viên hiểu rõ mối quan hệ giữa các lớp.
- Là cầu nối giữa **phân tích nghiệp vụ và lập trình**.

### ⚙️ Thành Phần Cơ Bản
| Thành phần | Ý nghĩa | Ví dụ |
|-------------|----------|-------|
| Class | Lớp đối tượng | Student, Course |
| Attribute | Dữ liệu của lớp | name, email |
| Method | Hành động của lớp | registerCourse() |
| Association | Quan hệ giữa lớp | Student – Course |
| Inheritance | Kế thừa lớp | Teacher extends Person |
| Multiplicity | Bội số | 1, *, 1..*, 0..1 |

---

## ⚖️ So Sánh ERD Và Class Diagram

| Tiêu chí | ERD | Class Diagram |
|-----------|------|----------------|
| Mục tiêu | Thiết kế cơ sở dữ liệu | Thiết kế hướng đối tượng |
| Mô hình hóa | Thực thể, thuộc tính, quan hệ | Lớp, thuộc tính, phương thức |
| Mức độ trừu tượng | Mức dữ liệu | Mức logic & hành vi |
| Mối quan hệ | 1:1, 1:N, N:M | Association, Aggregation, Inheritance |
| Giai đoạn dùng | Phân tích & thiết kế CSDL | Phân tích & thiết kế phần mềm |
| Kết quả | Database Schema | Cấu trúc code |

---

## 🔄 Liên Hệ Giữa ERD Và Class Diagram
- **ERD**: Dùng ở tầng **Data Layer (cơ sở dữ liệu)**.
- **Class Diagram**: Dùng ở tầng **Business Layer (logic ứng dụng)**.
- Trong ORM (Hibernate, JPA, Entity Framework):
    - Class ↔ Table
    - Attribute ↔ Column
    - Association ↔ Foreign Key

---

## 🧭 Kết Luận
- **ERD** tập trung vào dữ liệu, đảm bảo **toàn vẹn và logic dữ liệu**.
- **Class Diagram** tập trung vào cấu trúc và hành vi của đối tượng.
- Kết hợp cả hai giúp **xây dựng hệ thống toàn diện và bền vững**.
- 
# 📘 Lesson2: Các Thành Phần Chính Trong ERD

## 🧩 Giới Thiệu
ERD (Entity Relationship Diagram – Sơ đồ thực thể - quan hệ) là công cụ giúp **hiểu và mô hình hóa dữ liệu** của hệ thống.  
Nó thể hiện rõ **các thực thể, thuộc tính và mối quan hệ** giữa chúng trước khi triển khai cơ sở dữ liệu thực tế.

### 🎯 Tầm Quan Trọng
- Giúp hiểu cấu trúc dữ liệu logic trước khi viết code.
- Tránh trùng lặp, lỗi dữ liệu, và tăng khả năng mở rộng hệ thống.

---

## 🧱 1. Entity (Thực thể)

**Định nghĩa:**  
Là đối tượng hoặc khái niệm có thể lưu trữ thông tin trong cơ sở dữ liệu.  
Mỗi Entity thường tương ứng với **một bảng (table)** trong database.

**Đặc điểm:**
- Đại diện cho **một nhóm đối tượng cùng loại**.
- Mỗi dòng dữ liệu (record) là **một instance** của entity.

**Ví dụ:**  
Entity: `Student`  
Thuộc tính: `student_id`, `name`, `email`, `date_of_birth`  
→ Mỗi sinh viên là một dòng trong bảng `Student`.

---

## 🧾 2. Attribute (Thuộc tính)

**Định nghĩa:**  
Là thông tin mô tả đặc điểm hoặc tính chất của một Entity hoặc Relationship.

**Phân loại thuộc tính:**
| Loại | Mô tả | Ví dụ |
|------|-------|--------|
| Simple Attribute | Thuộc tính cơ bản | `name`, `age` |
| Composite Attribute | Gồm nhiều phần nhỏ | `FullName` = `FirstName` + `LastName` |
| Derived Attribute | Tính từ thuộc tính khác | `Age` từ `DateOfBirth` |
| Key Attribute | Định danh duy nhất | `student_id` |

**Ví dụ:**
- `date_of_birth` → thuộc tính cơ bản.
- `age` → thuộc tính dẫn xuất (derived).

---

## 🔗 3. Relationship (Mối quan hệ)

**Định nghĩa:**  
Là **liên kết giữa các thực thể** trong hệ thống.

**Phân loại theo số lượng (Cardinality):**
| Loại quan hệ | Mô tả | Ví dụ |
|---------------|--------|--------|
| 1–1 (One to One) | Một A liên kết với một B | `User` – `Profile` |
| 1–N (One to Many) | Một A liên kết nhiều B | `Teacher` – `Course` |
| N–N (Many to Many) | Nhiều A liên kết nhiều B | `Student` – `Course` |

**Ví dụ minh họa:**  
`Student` và `Course` có quan hệ N–N  
→ Bảng trung gian `Enrollment` giúp ánh xạ mối quan hệ và lưu thêm thông tin như `date_enrolled`, `grade`.

---

## ⚙️ 4. Biểu Diễn Trong ERD

| Thành phần | Ký hiệu | Ý nghĩa | Ví dụ |
|-------------|----------|----------|--------|
| Entity | Hình chữ nhật | Đại diện cho đối tượng | `Student`, `Course` |
| Attribute | Hình oval (bầu dục) | Mô tả đặc điểm | `name`, `email` |
| Relationship | Hình thoi (diamond) | Liên kết giữa các Entity | `enrolls`, `teaches` |

---

## 📖 5. Kiến Thức Mở Rộng

### 🔸 Cardinality (Bậc quan hệ)
- Cho biết **số lượng đối tượng được liên kết** giữa các thực thể.
- Ba loại phổ biến: 1:1, 1:N, N:N.

### 🔸 Relationship Entity (Bảng trung gian)
- Một số mối quan hệ N–N cần có bảng trung gian để lưu dữ liệu bổ sung.
- Ví dụ: Bảng `Enrollment` lưu thêm `date_enrolled`, `grade`.

---

## 🧭 6. Kết Luận
- ERD mô tả **Entity – Attribute – Relationship**, là nền tảng để **thiết kế cơ sở dữ liệu logic**.
- Hiểu rõ các thành phần giúp đảm bảo **tính toàn vẹn dữ liệu và khả năng mở rộng hệ thống**.

# 📘 Lesson3: Mối Quan Hệ Trong Thiết Kế ERD (Relationship)

## 🧩 Giới Thiệu
Khi thiết kế cơ sở dữ liệu, việc xác định **mối quan hệ (Relationship)** giữa các thực thể là bước quan trọng để đảm bảo hệ thống phản ánh đúng **logic nghiệp vụ**.

Nếu xác định sai hoặc bỏ qua mối quan hệ:
- Dữ liệu bị **trùng lặp (redundancy)**.
- Các bảng không thể liên kết đúng.
- Hệ thống **khó bảo trì hoặc mở rộng** sau này.

**Ví dụ:**  
Một **Student** có thể đăng ký nhiều **Course**, và mỗi **Course** có nhiều **Student** → mối quan hệ **N–N (nhiều–nhiều)** cần được mô hình hóa đúng.

---

## 🔗 Khái Niệm Relationship
**Định nghĩa:**  
Relationship là **liên kết logic** giữa hai hoặc nhiều **Entity**, thể hiện cách các đối tượng tương tác hoặc phụ thuộc lẫn nhau.

**Đặc điểm:**
- Biểu diễn bằng **hình thoi (diamond)** trong ERD.
- Kết nối giữa các Entity.
- Có thể có **thuộc tính riêng** (relationship attributes).

**Ví dụ:**  
`Student` ↔ `Enrolls` ↔ `Course`  
→ Mối quan hệ “Enrolls” thể hiện việc sinh viên đăng ký môn học.  
→ Khi triển khai, tạo bảng trung gian `Enrollment(student_id, course_id, enroll_date, grade)`.

---

## ⚙️ Các Loại Mối Quan Hệ Trong ERD

### 1️⃣ One-to-One (1–1)
**Định nghĩa:**  
Mỗi bản ghi trong A chỉ liên kết với **một** bản ghi trong B, và ngược lại.

**Ví dụ:**  
`Employee` ↔ `IDCard`  
→ Mỗi nhân viên có 1 thẻ duy nhất.  
→ Mỗi thẻ chỉ thuộc về 1 nhân viên.

**Triển khai:**  
Có thể gộp bảng hoặc sử dụng **Foreign Key 1–1**.

---

### 2️⃣ One-to-Many (1–N)
**Định nghĩa:**  
Một bản ghi trong A có thể liên kết với **nhiều** bản ghi trong B, nhưng mỗi bản ghi trong B chỉ thuộc **một** bản ghi trong A.

**Ví dụ:**  
`Department` ↔ `Teacher`  
→ Một khoa có nhiều giảng viên.  
→ Mỗi giảng viên chỉ thuộc một khoa.

**Triển khai:**  
Thêm **FK `department_id`** trong bảng `Teacher`.

---

### 3️⃣ Many-to-Many (N–N)
**Định nghĩa:**  
Một bản ghi trong A có thể liên kết với **nhiều** bản ghi trong B và ngược lại.

**Ví dụ:**  
`Student` ↔ `Course`  
→ Nhiều sinh viên học nhiều môn.  
→ Nhiều môn có nhiều sinh viên.

**Triển khai:**  
Cần tạo **bảng trung gian (Associative Entity)**, ví dụ:  
`Enrollment(student_id, course_id, enroll_date, grade)`.

---

## 🧾 Thuộc Tính Của Relationship
**Định nghĩa:**  
Relationship có thể chứa **thuộc tính riêng**, mô tả thông tin đặc trưng của mối liên kết giữa các thực thể.

**Ví dụ:**  
Trong `Enrolls(Student, Course)` → thuộc tính:
- `enroll_date`
- `grade`

→ Các thuộc tính này **không thuộc riêng Student hay Course** mà thuộc về **mối quan hệ**.

---

## 🧮 Cardinality & Participation

### 🔸 Cardinality (Bội số quan hệ)
Biểu diễn **số lượng thực thể** có thể tham gia vào mối quan hệ.

| Ký hiệu | Ý nghĩa |
|----------|----------|
| (1,1) | Chính xác một thực thể |
| (0,N) | Có thể không có hoặc nhiều thực thể |
| (1,N) | Phải có ít nhất một, có thể nhiều thực thể |

### 🔸 Participation (Mức độ tham gia)
Cho biết thực thể **có bắt buộc** tham gia mối quan hệ hay không:
- **Total participation:** tất cả thực thể đều tham gia.
- **Partial participation:** chỉ một phần thực thể tham gia.

---

## 📊 So Sánh Các Loại Quan Hệ

| Loại Quan Hệ | Ký Hiệu | Mô Tả | Ví Dụ |
|---------------|---------|--------|--------|
| 1–1 | (1,1) – (1,1) | Một – Một | Nhân viên ↔ Thẻ nhân viên |
| 1–N | (1,1) – (0,N) | Một – Nhiều | Khoa ↔ Giảng viên |
| N–N | (0,N) – (0,N) | Nhiều – Nhiều | Sinh viên ↔ Môn học |

---

## 🧭 Kết Luận
- Relationship là **nền tảng của ERD**, giúp xác định **liên kết dữ liệu** giữa các bảng.
- Cần **xác định đúng loại quan hệ (1–1, 1–N, N–N)** để thiết kế cơ sở dữ liệu **chính xác và dễ mở rộng**.
- Các mối quan hệ phức tạp có thể cần **bảng trung gian** để lưu thông tin chi tiết như ngày tạo, điểm, hoặc trạng thái.

# 📘 Lesson4: Chuẩn Hóa Dữ Liệu (Normalization)

## 🧩 Giới Thiệu
Trong thiết kế cơ sở dữ liệu, dữ liệu có thể bị **trùng lặp**, **không nhất quán**, hoặc **khó mở rộng** nếu không được tổ chức hợp lý.  
**Chuẩn hóa dữ liệu (Normalization)** là quy trình phân tách bảng lớn thành các bảng nhỏ hơn và xác định mối quan hệ giữa chúng, giúp:
- Loại bỏ sự dư thừa dữ liệu.
- Đảm bảo tính toàn vẹn dữ liệu.
- Tối ưu khả năng bảo trì và lưu trữ.

**Ví dụ:**  
Bảng lưu thông tin sinh viên chứa cả “Tên giảng viên” lặp lại nhiều lần → nếu giảng viên đổi tên, cần sửa nhiều dòng → dễ sai.  
→ Chuẩn hóa tách dữ liệu thành các bảng riêng: Student, Course, Instructor.

---

## 🧠 Định Nghĩa
Chuẩn hóa dữ liệu là quá trình **tổ chức dữ liệu** trong cơ sở dữ liệu nhằm:
- Giảm dư thừa dữ liệu.
- Đảm bảo logic dữ liệu.
- Dễ bảo trì và mở rộng hệ thống.

### 🎯 Mục Tiêu
| Mục tiêu | Mô tả |
|-----------|-------|
| Giảm dư thừa dữ liệu | Mỗi thông tin chỉ lưu một lần duy nhất |
| Tránh bất nhất dữ liệu | Cập nhật một nơi, không mâu thuẫn ở nơi khác |
| Dễ bảo trì, mở rộng | Dễ thay đổi cấu trúc |
| Cải thiện hiệu suất truy vấn | Giảm kích thước bảng, tối ưu hiệu năng |

---

## 🔍 Các Khái Niệm Cơ Bản
- **Thuộc tính (Attribute):** Cột dữ liệu.
- **Khóa chính (Primary Key):** Xác định duy nhất mỗi dòng dữ liệu.
- **Phụ thuộc hàm (Functional Dependency):** Mối quan hệ giữa các thuộc tính.
  - Ví dụ: `StudentID → StudentName` nghĩa là StudentID xác định duy nhất StudentName.

---

## 📊 Các Dạng Chuẩn (Normal Forms)

### 1️⃣ Dạng Chuẩn Thứ Nhất – 1NF (First Normal Form)
**Điều kiện:**
- Mỗi ô chỉ chứa **một giá trị duy nhất** (atomic value).
- Không có nhóm lặp.

**Ví dụ sai:**  
Một cột chứa danh sách nhiều giá trị.  
**Chuẩn hóa:**  
Tách ra sao cho mỗi hàng chỉ chứa **một giá trị duy nhất** trên mỗi cột.

---

### 2️⃣ Dạng Chuẩn Thứ Hai – 2NF (Second Normal Form)
**Điều kiện:**
- Bảng đã đạt **1NF**.
- Mọi thuộc tính **phụ thuộc hoàn toàn vào khóa chính**, không phụ thuộc **một phần**.

**Ví dụ sai:**  
`StudentID, CourseID → Grade`  
Nhưng `StudentName` chỉ phụ thuộc `StudentID`.  
→ Sai 2NF vì phụ thuộc một phần.

**Chuẩn hóa:**  
Tách thành các bảng nhỏ hơn:
- `Student(StudentID, StudentName)`
- `Course(CourseID, CourseName)`
- `Enrollment(StudentID, CourseID)`

---

### 3️⃣ Dạng Chuẩn Thứ Ba – 3NF (Third Normal Form)
**Điều kiện:**
- Đạt **2NF**.
- Không có **phụ thuộc bắc cầu (Transitive Dependency)**.

**Ví dụ sai:**  
`StudentID → DepartmentID → DepartmentName`  
→ `StudentID` gián tiếp xác định `DepartmentName`.  
→ Sai 3NF.

**Chuẩn hóa:**
- `Student(StudentID, StudentName, DepartmentID)`
- `Department(DepartmentID, DepartmentName)`

---

### 4️⃣ Dạng Chuẩn Boyce–Codd (BCNF)
**Điều kiện:**
- Với mọi phụ thuộc hàm `X → Y`, thì `X` phải là **siêu khóa (superkey)**.  
  BCNF chặt chẽ hơn 3NF, loại bỏ các phụ thuộc đặc biệt còn sót lại.

---

## 🧮 Ví Dụ Tổng Hợp
**Trước chuẩn hóa:**  
`StudentID, StudentName, CourseName, Instructor`

**Sau chuẩn hóa (3NF):**
- `Student(StudentID, StudentName)`
- `Course(CourseID, CourseName, Instructor)`
- `Enrollment(StudentID, CourseID)`

✅ Kết quả: Không dư thừa, dữ liệu logic, rõ ràng.

---

## ⚖️ So Sánh Các Dạng Chuẩn

| Dạng chuẩn | Điều kiện chính | Mục tiêu đạt được | Vấn đề còn tồn tại |
|-------------|----------------|-------------------|--------------------|
| 1NF | Mỗi ô chỉ chứa 1 giá trị | Loại bỏ nhóm lặp | Còn phụ thuộc 1 phần |
| 2NF | Không phụ thuộc 1 phần vào khóa chính | Giảm dư thừa thuộc tính phụ | Còn phụ thuộc bắc cầu |
| 3NF | Không có phụ thuộc bắc cầu | Dữ liệu sạch, logic | Một số phụ thuộc đặc biệt |
| BCNF | Mọi phụ thuộc X → Y, X là siêu khóa | Tối ưu nhất | Thiết kế phức tạp hơn |

---

## 💡 Kiến Thức Mở Rộng
- **Phụ thuộc bắc cầu:** Nếu `A → B` và `B → C` thì `A → C`.
- **Phi chuẩn hóa (Denormalization):** Là quá trình **kết hợp bảng** để **tăng tốc truy vấn**, chấp nhận dư thừa dữ liệu — dùng khi ưu tiên tốc độ hơn tính toàn vẹn.

---

## 🧭 Kết Luận
Chuẩn hóa dữ liệu giúp:
- Cơ sở dữ liệu **tinh gọn, nhất quán và logic**.
- Tránh trùng lặp, tối ưu bảo trì và mở rộng.
- Là **nền tảng quan trọng** trong thiết kế hệ thống dữ liệu chuyên nghiệp.