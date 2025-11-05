# Lesson1: Tổng quan về SRS (Software Requirements Specification)

## 1. Khái niệm
**SRS (Software Requirements Specification)** là tài liệu chính thức mô tả **toàn bộ yêu cầu của hệ thống phần mềm** sẽ được xây dựng.  
→ Là **kết quả đầu ra quan trọng nhất** của giai đoạn *Phân tích yêu cầu*.

---

## 2. Mục tiêu của SRS
- **WHAT:** Hệ thống sẽ làm gì.
- **WHO:** Ai sẽ sử dụng hệ thống.
- **WHY:** Vì sao hệ thống cần được xây dựng.

> ⚠️ Lưu ý: SRS chỉ trả lời “WHAT” – không mô tả “HOW” (cách thực hiện).

---

## 3. Ba câu hỏi cốt lõi trong SRS

### 3.1 WHAT – Hệ thống làm gì?
Mô tả:
- **Yêu cầu chức năng (Functional Requirements):** Tính năng hệ thống phải có.
- **Yêu cầu phi chức năng (Non-functional Requirements):** Hiệu năng, bảo mật, khả năng mở rộng, khả năng sử dụng,...

**Ví dụ:**
- Hệ thống cho phép đăng nhập bằng tài khoản Google.
- Trang web phản hồi ≤ 2 giây với 1000 người dùng đồng thời.

---

### 3.2 WHO – Ai sử dụng hệ thống?
Xác định **các bên liên quan (stakeholders):**
- Người dùng cuối (end-user)
- Quản trị viên hệ thống
- Khách hàng doanh nghiệp

→ Mỗi nhóm có mục tiêu và nhu cầu khác nhau.

---

### 3.3 WHY – Tại sao cần hệ thống này?
Trình bày:
- **Bối cảnh, vấn đề hiện tại**
- **Mục tiêu kinh doanh**
- **Lợi ích cụ thể**

**Ví dụ:**  
Hiện tại việc đặt phòng khách sạn thủ công gây tốn thời gian và dễ sai sót → Hệ thống đặt phòng trực tuyến giúp tự động hóa, giảm thời gian từ 30 phút xuống 3 phút.

---

## 4. Vai trò của tài liệu SRS
SRS là **“bản hợp đồng” giữa khách hàng và đội ngũ phát triển**.

- **Đối với khách hàng:**  
  Xác nhận yêu cầu đã được hiểu đúng, đủ.  
  Là cơ sở để ký duyệt và kiểm soát phạm vi dự án.

- **Đối với đội phát triển:**  
  Hướng dẫn cho các giai đoạn thiết kế, lập trình, kiểm thử.  
  Căn cứ từ chối yêu cầu phát sinh (scope creep).  
  Cơ sở cho quy trình quản lý thay đổi (change control).

---

## 5. Kết luận
Một tài liệu SRS tốt giúp:
- Khách hàng hiểu và tin tưởng dự án.
- Đội phát triển có định hướng rõ ràng.
- Giảm rủi ro, tiết kiệm chi phí và thời gian phát triển.

---

# Lesson2: Vai trò của SRS trong quy trình phát triển phần mềm

## 1. Giới thiệu
**SRS (Software Requirements Specification)** không chỉ là tài liệu yêu cầu phần mềm, mà còn là **trung tâm giao tiếp** giữa các bên trong dự án: khách hàng, quản lý dự án, lập trình viên, và kiểm thử viên.  
Nó đảm bảo tất cả thành viên hiểu đúng, thống nhất và có căn cứ rõ ràng trong suốt vòng đời phát triển phần mềm.

---

## 2. Vai trò của SRS đối với từng bên trong dự án

### A. Đối với Khách hàng và Người dùng cuối
- **Xác nhận yêu cầu:** Giúp khách hàng kiểm chứng rằng hệ thống đúng với mong muốn của họ.
- **Bằng chứng pháp lý:** Cơ sở nghiệm thu sản phẩm. Nếu phần mềm không đáp ứng SRS, khách hàng có quyền từ chối.
- **Lá chắn bảo vệ:** Tránh tranh cãi kiểu “tôi tưởng tính năng này có”.  
  → Từ ý tưởng mơ hồ (“Tôi muốn phần mềm quản lý tốt hơn”) → thành yêu cầu cụ thể (“5 báo cáo doanh thu, phân quyền 3 cấp, xuất file Excel”).

---

### B. Đối với Quản lý Dự án (PM)
SRS là **bản đồ chỉ đường** của dự án, giúp PM quản lý hiệu quả ở 3 khía cạnh:

1. **Xác định phạm vi (Scope):**  
   Mọi yêu cầu trong SRS là phạm vi dự án; ngoài ra cần thương lượng lại → chống *scope creep* (yêu cầu thêm không kiểm soát).

2. **Lập kế hoạch & Ước tính:**
    - Dựa vào độ phức tạp của yêu cầu để chia công việc.
    - Ước tính chi phí, thời gian, nguồn lực và kỹ năng cần thiết.

3. **Quản lý thay đổi:**  
   Khi có yêu cầu mới → so sánh với SRS gốc → đánh giá tác động (chức năng, thời gian, chi phí).

---

### C. Đối với Đội ngũ Phát triển (Developers)
- **SRS là “Single Source of Truth” (nguồn chân lý duy nhất).**  
  Giúp toàn bộ lập trình viên hiểu cùng một yêu cầu, tránh code sai lệch.
- Là **đầu vào cho thiết kế kỹ thuật:**
    - Yêu cầu chức năng → sinh Use Case Diagram.
    - Danh từ trong SRS → sinh Class Diagram.
    - Mô tả dữ liệu → sinh ERD.
- Ảnh hưởng đến **quyết định kỹ thuật:**  
  Các yêu cầu phi chức năng (hiệu năng, bảo mật, mở rộng) định hướng công nghệ, kiến trúc, framework.

---

### D. Đối với Đội ngũ Kiểm thử (QA/Testers)
- Dùng SRS để **viết kịch bản kiểm thử (test case)**.  
  Ví dụ:
  > Yêu cầu: “Mật khẩu ≥ 8 ký tự, có chữ hoa, chữ thường, số.”  
  > → Tester tạo test case TC1, TC2, TC3 tương ứng để kiểm tra đúng/sai.
- SRS là **căn cứ xác định lỗi:** Khi phần mềm không tuân theo yêu cầu trong SRS.

---

## 3. Kết luận
Một tài liệu **SRS rõ ràng và chi tiết**:
- Giúp khách hàng yên tâm và kiểm soát yêu cầu.
- Giúp PM lập kế hoạch và quản lý phạm vi dự án.
- Giúp dev và QA có cơ sở thống nhất trong phát triển và kiểm thử.  
  → Là yếu tố then chốt đảm bảo **thành công và minh bạch** trong toàn bộ quy trình phát triển phần mềm.

---