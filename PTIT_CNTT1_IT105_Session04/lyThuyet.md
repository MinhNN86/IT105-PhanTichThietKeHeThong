Lession 01: Tổng quan về Class trong UML 1. Mở đầu
Use Case Diagram cho biết hệ thống làm gì, còn Class Diagram cho biết hệ thống gồm những phần nào và chúng liên kết ra sao.
Đây là bước chuyển từ phân tích chức năng sang phân tích cấu trúc.

    2. Tại sao cần Class Diagram
        •	Giống như bản vẽ kết cấu của ngôi nhà (so với Use Case là bản công năng).
        •	Mô tả “bộ xương dữ liệu” – các thành phần chính và mối quan hệ giữa chúng.

    3. Khái niệm Class
        •	Class (Lớp): khuôn mẫu mô tả nhóm đối tượng có cùng đặc điểm và hành vi.
        •	Object (Đối tượng): thể hiện cụ thể được tạo từ Class.

    4. Biểu diễn Class trong UML
        Class được vẽ bằng hình chữ nhật chia 3 phần:
            1. Tên lớp (viết hoa chữ đầu) → Student
            2. Thuộc tính → code, name, date
            3. Phương thức → courseRegistration(), seeScore()

    5. Vai trò của Class Diagram
        🧩 Cầu nối giữa phân tích và lập trình → giúp dev hiểu cấu trúc.
        🗃️ Cơ sở thiết kế database → Class → bảng dữ liệu.
        👥 Hỗ trợ làm việc nhóm → có sơ đồ chung để thống nhất và giảm lỗi.
        🔧 Dễ bảo trì và mở rộng → người mới xem sơ đồ là hiểu cấu trúc hệ thống.

    6. Kết luận
        Class Diagram mô tả cấu trúc dữ liệu và mối quan hệ giữa các phần trong hệ thống.
        Hiểu rõ Class (khuôn mẫu) và Object (đối tượng cụ thể) là nền tảng của lập trình hướng đối tượng và thiết kế phần mềm chuyên nghiệp.

Lession 02: các thành phần của class 1. Class là gì
Class là bản thiết kế cho các đối tượng trong hệ thống, mô tả:
• Thuộc tính (Attributes): điều mà đối tượng biết.
• Phương thức (Methods): điều mà đối tượng làm được.

    Ví dụ: Class SinhVien có thuộc tính studentCode, name, date và phương thức registerForCourses(), seeScore().

    2. Thuộc tính (Attributes)
        •	Trả lời câu hỏi: “Đối tượng biết gì?”
        •	Cú pháp UML: visibility name: type = defaultValue
        •	+ public – dùng được ở mọi nơi
        •	- private – chỉ dùng trong class

    3. Phương thức (Methods)
        •	Trả lời câu hỏi: “Đối tượng làm được gì?”
        •	Cú pháp UML: visibility name(parameterList): returnType

    4. Thành phần Static
        •	Là thuộc tính hoặc phương thức dùng chung cho mọi đối tượng.
        •	Ký hiệu: gạch chân trong UML.

    5. Thành phần Abstract (Trừu tượng)
        •	Class hoặc phương thức chưa có phần cài đặt cụ thể.
        •	Dùng khi Class cha chỉ định nghĩa hành động chung, Class con sẽ tự triển khai.

    6. Kết luận
        •	Thuộc tính: điều đối tượng biết.
        •	Phương thức: điều đối tượng làm được.
        •	Static: dùng chung cho tất cả.
        •	Abstract: khuôn hành động chung, chưa có nội dung cụ thể.

Lession 03: BỔ TỪ TRUY CẬP (ACCESS MODIFIERS) VÀ TÍNH ĐÓNG GÓI 1. Mở đầu
Ký hiệu +, -, #, ~ trong UML thể hiện mức độ truy cập của thuộc tính hoặc phương thức.
Chúng là “ổ khóa” bảo vệ dữ liệu, giúp hệ thống an toàn, dễ bảo trì và chuyên nghiệp hơn.

    2. Khái niệm tính đóng gói (Encapsulation)
        •	Là nguyên tắc che giấu dữ liệu, chỉ cho phép truy cập qua các phương thức được kiểm soát.
        •	Giống như viên thuốc con nhộng: người dùng chỉ “uống” (sử dụng hàm), không tự ý “mở ra” (truy cập trực tiếp dữ liệu).
        •	Giúp bảo vệ dữ liệu, giảm lỗi và dễ quản lý mã nguồn.

    3. Các mức độ truy cập (Access Modifiers)
        •	public (+): công khai, ai cũng có thể truy cập.
        •	private (-): riêng tư, chỉ class đó truy cập được.
        •	protected (#): lớp con hoặc class trong cùng package có thể truy cập.
        •	package (~): chỉ các class trong cùng package truy cập được.

    4. Getter và Setter
        •	Getter: cho phép đọc giá trị thuộc tính (getName()).
        •	Setter: cho phép chỉnh sửa có kiểm soát (setScore()), tránh lỗi như nhập điểm âm.

    5. Protected và Package
        •	Protected: chia sẻ nội bộ trong hệ thống kế thừa (giống “chìa khóa gia đình”).
        •	Package: chia sẻ trong cùng nhóm class (giống “chìa khóa hàng xóm”).

    6. Kết luận
    Tính đóng gói và mức độ truy cập giúp:
        •	Bảo vệ dữ liệu khỏi truy cập sai.
        •	Giảm lỗi, dễ bảo trì.
        •	Giữ mã nguồn gọn gàng, có tổ chức.

Lession 04: Mối quan hệ giữa các class (Association, Dependency, Generalization, Aggregation, Composition)

Quan hệ cấu trúc (Structural):

    Association: Hai lớp biết nhau, tồn tại lâu dài.

    Directed Association: Liên kết một chiều (một lớp biết lớp kia).

    Aggregation: Quan hệ “có” nhưng độc lập (thoi rỗng).

    Composition: Quan hệ “chứa” nhưng phụ thuộc chặt chẽ (thoi đặc).

Quan hệ phân loại (Classification):

    Generalization: Kế thừa (“là một loại của”).

    Realization: Class hiện thực hóa interface (“có thể làm điều đó”).

Quan hệ phụ thuộc (Dependency):

    Dependency: Phụ thuộc tạm thời giữa hai lớp.

    Usage: Dạng phụ thuộc ngắn hạn (thường ký hiệu <<use>>).

Bảng tổng hợp các mối quan hệ

<table border="1" cellspacing="0" cellpadding="6">
  <thead>
    <tr>
      <th>Loại quan hệ</th>
      <th>Ký hiệu UML</th>
      <th>Mức độ gắn bó</th>
      <th>Ví dụ</th>
      <th>Ý nghĩa</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Association</td>
      <td>──</td>
      <td>Vừa phải</td>
      <td>Student – Class</td>
      <td>Hai bên biết nhau, liên kết lâu dài</td>
    </tr>
    <tr>
      <td>Directed Association</td>
      <td>→</td>
      <td>Một chiều</td>
      <td>Order → Customer</td>
      <td>Chỉ một bên biết bên kia</td>
    </tr>
    <tr>
      <td>Aggregation</td>
      <td>◇──</td>
      <td>Lỏng lẻo</td>
      <td>Department – Staff</td>
      <td>Quan hệ “có” nhưng độc lập</td>
    </tr>
    <tr>
      <td>Composition</td>
      <td>◆──</td>
      <td>Rất chặt chẽ</td>
      <td>House – Room</td>
      <td>Phụ thuộc hoàn toàn, “chết chung”</td>
    </tr>
    <tr>
      <td>Generalization</td>
      <td>▲</td>
      <td>Mạnh</td>
      <td>Warrior – Character</td>
      <td>Là một loại của (kế thừa)</td>
    </tr>
    <tr>
      <td>Realization</td>
      <td>△</td>
      <td>Trung bình</td>
      <td>Bird – ICanFly</td>
      <td>Hiện thực hóa interface</td>
    </tr>
    <tr>
      <td>Dependency</td>
      <td>──▶ (nét đứt)</td>
      <td>Yếu</td>
      <td>Report – Printer</td>
      <td>Phụ thuộc tạm thời</td>
    </tr>
    <tr>
      <td>Usage</td>
      <td>&lt;&lt;use&gt;&gt;</td>
      <td>Rất yếu</td>
      <td>Patient – BloodPressureMonitor</td>
      <td>Dùng tạm thời, không sở hữu nhau</td>
    </tr>
  </tbody>
</table>

Lession 05: Bội số trong mối quan hệ (Multiplicity) (1-1, 1-N, N-N) 1. Vì sao cần Multiplicity
Khi nói “Lớp học có Sinh viên”, ta cần biết có bao nhiêu sinh viên – 1, nhiều, hay giới hạn cụ thể.
Multiplicity giúp thể hiện số lượng đối tượng liên kết giữa các class, làm bản thiết kế rõ ràng, chính xác và phản ánh đúng quy tắc nghiệp vụ.

    Ví dụ: Một lớp có ít nhất 1 sinh viên, tối đa 50; một sinh viên học tối đa 8 môn.

    2. Khái niệm
    Multiplicity là số lượng đối tượng của một lớp có thể liên kết với một đối tượng của lớp khác.
    Luôn đọc theo hướng mũi tên:
        •	Từ A nhìn sang B thấy 0..* → “Một A có thể liên kết với 0 hoặc nhiều B.”
        •	Từ B nhìn sang A thấy 1 → “Mỗi B chỉ thuộc về 1 A duy nhất.”

    3. Các ký hiệu phổ biến
        •	1 → Chính xác một (VD: Người có 1 CMND).
        •	0..1 → Không hoặc một (VD: Nhân viên có thể có hoặc không có máy tính).
        •	* hoặc 0..* → Không hoặc nhiều (VD: Khách hàng có nhiều đơn hàng).
        •	1..* → Một hoặc nhiều (VD: Lớp học có ít nhất 1 sinh viên).
        •	m..n → Từ m đến n (VD: Lớp học có 25–40 sinh viên).

    4. Các loại quan hệ theo Multiplicity
        •	1–1: Một – Một (VD: Người – CCCD).
        •	1–N: Một – Nhiều (VD: Khách hàng – Đơn hàng, Lớp – Sinh viên).
        •	N–N: Nhiều – Nhiều (VD: Sinh viên – Môn học).
    → Trong cơ sở dữ liệu, phải tạo bảng trung gian để tách N–N thành hai quan hệ 1–N.

    5. Vai trò của Multiplicity
        •	Giúp mô tả chính xác quy tắc nghiệp vụ, tránh hiểu sai.
        •	Hỗ trợ thiết kế cơ sở dữ liệu đúng đắn (bảng trung gian, khóa ngoại…).
        •	Hướng dẫn lập trình viên chọn đúng kiểu dữ liệu (biến đơn, mảng, danh sách…).

    6. Kết luận
    Multiplicity cho biết số lượng mối liên kết giữa các class, giúp thiết kế rõ ràng – chính xác – dễ cài đặt.
    📌 Nhớ nhanh:
    1 → Một
    0..1 → Có thể có hoặc không
    * → Không giới hạn
    1..* → Ít nhất một
    m..n → Giới hạn cụ thể

Lession 06: Từ Use Case → Class Diagram
Mục tiêu
• Rút Class từ Use Case bằng kỹ thuật Noun–Verb.
• Thực hành quy trình 3 bước: Tìm → Sàng lọc → Lắp ghép.
• Vẽ sơ khởi Class Diagram với quan hệ và multiplicity.

    Ý tưởng cốt lõi (Noun–Verb)
        •	Danh từ (Noun) → ứng viên Class hoặc thuộc tính.
        •	Động từ (Verb) → gợi ý phương thức hoặc mối quan hệ.
        •	Danh từ chỉ là ứng viên → phải sàng lọc trước khi thành Class.

    Quy trình 3 bước
        1.	Tìm (Identify): Gạch chân mọi danh từ và động từ trong Use Case.
        2.	Sàng lọc (Filter):
        •	Giữ thực thể nghiệp vụ có ý nghĩa độc lập (có dữ liệu/hành vi) → Class.
        •	Chuyển các mô tả như code, name, numberOfCredits thành thuộc tính, loại bỏ danh từ quá chung (System) hay kỹ thuật (List).
        •	Những sự kiện/phiên (phiếu/đơn/biên lai) thường xứng đáng là Class nếu có dữ liệu/đời sống riêng.
        3.	Lắp ghép (Assemble):
        •	Gán thuộc tính vào Class phù hợp.
        •	Dùng động từ để xác định phương thức và quan hệ (Association/Aggregation/Composition/Dependency).
        •	Đặt Multiplicity (1, 0..1, 0.., 1.., m..n).
        •	Phát hiện N–N → tạo Class trung gian để lưu thông tin phiên.

    Ví dụ nhanh (Use Case: Register For Courses)
        •	Tìm: Student, Course, Subject, RegistrationForm, code, name, numberOfCredits, schoolSchedule, register, result…
        •	Sàng lọc:
        •	Giữ Class: Student, Course, Subject, RegistrationForm.
        •	Thuộc tính: code, name, numberOfCredits → Subject; schoolSchedule → Course; result → RegistrationForm.
        •	Lắp ghép:
        •	Subject 1 — * Course (một môn có nhiều lớp phần).
        •	Student * — * Course → N–N ⇒ dùng RegistrationForm làm Class trung gian:
        •	Student 1 — * RegistrationForm ** * — 1 Course**.
        •	Phương thức gợi ý: Student.register(Course), RegistrationForm.result(...).

    Checklist nhanh
        •	Gạch chân tất cả danh từ/động từ trong mô tả.
        •	Loại danh từ chung chung/kỹ thuật, chuyển mô tả thành thuộc tính.
        •	Xem sự kiện/phiên (phiếu/biên lai/đơn) có dữ liệu/đời sống riêng → Class.
        •	Từ động từ: xác định quan hệ hoặc phương thức.
        •	Kiểm tra Multiplicity theo quy tắc nghiệp vụ; có N–N → thêm Class trung gian.

    Mẹo thực tế
        •	Dành thời gian cho sàng lọc và xác thực với chuyên gia nghiệp vụ.
        •	Khi phân vân Class vs thuộc tính, hỏi: “Nó có đời sống riêng không?”
        •	Ghi chú lý do giữ/loại từng ứng viên để dễ review và truy vết.

    Kết quả mong đợi
        •	Danh sách Class sơ khởi + thuộc tính cơ bản.
        •	Class Diagram thô (Class, quan hệ, multiplicity).
        •	Danh sách phương thức gợi ý và điểm cần xác thực (quy tắc nghiệp vụ, multiplicity).
