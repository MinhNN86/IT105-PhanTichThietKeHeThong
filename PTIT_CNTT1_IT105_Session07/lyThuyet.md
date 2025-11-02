# Lesson 1: Tổng quan về kiến trúc tổng thế của toàn bộ hệ thống

## 1. Tầm quan trọng

- Kiến trúc hệ thống là nền tảng quyết định **độ ổn định**, **khả năng mở rộng** và **dễ bảo trì** của phần mềm.
- Dù giao diện hay chức năng tốt đến đâu, nếu kiến trúc không hợp lý thì hệ thống sẽ khó mở rộng, dễ lỗi và kém hiệu năng.
- Hiểu kiến trúc giúp:
  - Nhìn tổng thể hệ thống, không sa vào chi tiết code.
  - Phân tách chức năng, vai trò từng tầng.
  - Hiểu cách các module tương tác.

## 2. Liên hệ thực tế

Giống như xây nhà — cần bản thiết kế tổng thể để xác định cấu trúc, đường điện nước, nền móng,...  
Một **kiến trúc phần mềm tốt** giúp các “phòng ban” (module) phối hợp hiệu quả, dễ mở rộng về sau.

## 3. Khái niệm kiến trúc hệ thống

- **Định nghĩa:** Cấu trúc logic và vật lý mô tả cách các thành phần phần mềm và phần cứng tương tác để đáp ứng yêu cầu nghiệp vụ.
- **Bao gồm:**
  - Phân tách tầng logic: `Presentation`, `Business`, `Data`.
  - Giao tiếp giữa các module qua `API`, `Event`, `Message`.
  - Quản lý truyền, lưu trữ và bảo mật dữ liệu.
- Mục tiêu: Giảm phụ thuộc giữa module, cho phép nhóm phát triển làm việc độc lập.

## 4. Ba tầng chính trong kiến trúc hệ thống

| Tầng               | Vai trò                    | Thành phần điển hình         | Ví dụ                   |
| ------------------ | -------------------------- | ---------------------------- | ----------------------- |
| **Presentation**   | Giao tiếp với người dùng   | HTML, JSP, React, Controller | Giao diện thêm sản phẩm |
| **Business Logic** | Xử lý nghiệp vụ, quy tắc   | Service, DTO                 | Kiểm tra giá sản phẩm   |
| **Data Access**    | Lưu trữ, truy xuất dữ liệu | Repository, DAO, Database    | Lưu sản phẩm vào DB     |

## 5. Ví dụ minh họa

**Ứng dụng quản lý sản phẩm**

- `Controller` gọi `createProduct()` khi người dùng thêm sản phẩm.
- `Service` kiểm tra dữ liệu hợp lệ.
- `Repository` lưu sản phẩm vào danh sách (hoặc DB).

➡️ Mỗi tầng có một **trách nhiệm riêng**, giúp dễ bảo trì, mở rộng, và giảm lỗi.

## 6. Các mô hình kiến trúc phổ biến

### 6.1 Monolithic Architecture

- Toàn bộ hệ thống nằm trong một khối duy nhất.
- Dễ phát triển ban đầu nhưng khó mở rộng về sau.

### 6.2 Microservices Architecture

- Chia nhỏ hệ thống thành nhiều dịch vụ độc lập.
- Dễ bảo trì và mở rộng, nhưng triển khai phức tạp.

### 6.3 Client–Server Architecture

- Phân tách giữa **Client (giao diện)** và **Server (xử lý nghiệp vụ)**.
- Là mô hình cơ bản trong các ứng dụng web hiện đại.

# Lesson 2: Kiến trúc 3 tầng (3-Tier Architecture)

## 1. Tầm quan trọng

- Giúp **giảm phụ thuộc giữa các phần**, **tăng khả năng mở rộng**, **dễ bảo trì**.
- Là mô hình phổ biến trong **ứng dụng web, thương mại điện tử, quản lý doanh nghiệp**.
- Mỗi tầng có **nhiệm vụ riêng**, phối hợp để hệ thống hoạt động ổn định.

## 2. Liên hệ thực tế

Ví dụ “**nhà hàng**”:

- **Nhân viên phục vụ** → _Presentation Layer_ (giao tiếp khách hàng).
- **Bếp** → _Business Logic Layer_ (xử lý yêu cầu, chế biến).
- **Kho hàng** → _Data Layer_ (lưu trữ nguyên liệu).

Tương tự, phần mềm cũng có ba tầng riêng biệt phối hợp cùng nhau.

## 3. Khái niệm

**Kiến trúc 3 tầng** là mô hình chia phần mềm thành ba tầng:

1. **Presentation Layer** – Tầng trình bày (giao tiếp người dùng).
2. **Business Logic Layer** – Tầng nghiệp vụ (xử lý chính).
3. **Data Access Layer** – Tầng dữ liệu (làm việc với DB, API).

👉 Mỗi tầng chỉ đảm nhận **một vai trò riêng**, giao tiếp **gián tiếp** qua tầng trung gian.

## 4. Cấu trúc chi tiết

### Presentation Layer

- Giao tiếp với người dùng, nhận input, gửi yêu cầu.
- Không xử lý nghiệp vụ.
- **Ví dụ:** HTML, React, Angular, Controller (Spring MVC).

### Business Logic Layer

- Xử lý quy tắc nghiệp vụ, tính toán, kiểm tra dữ liệu.
- **Ví dụ:** Service, Manager, Business Object.

### Data Access Layer

- Tương tác với cơ sở dữ liệu, file, hoặc API ngoài.
- Thực hiện CRUD và ẩn chi tiết dữ liệu.
- **Ví dụ:** Repository, DAO, ORM (Hibernate, JPA).

## 5. Luồng hoạt động

1. **Người dùng** gửi yêu cầu qua tầng Presentation.
2. **Business Layer** xử lý logic, xác thực, gọi Data Layer.
3. **Data Layer** thao tác DB rồi trả kết quả ngược lại.

## 6. Ví dụ minh họa

**Ứng dụng Quản lý Sản phẩm:**

- Controller nhận yêu cầu → gọi `createProduct()`.
- Service kiểm tra dữ liệu → áp dụng nghiệp vụ.
- Repository lưu sản phẩm vào DB.  
  ➡️ Code tách biệt rõ, dễ mở rộng và bảo trì.

## 7. So sánh giữa các tầng

| Tầng           | Mô tả                    | Vai trò chính                | Ví dụ            |
| -------------- | ------------------------ | ---------------------------- | ---------------- |
| Presentation   | Giao tiếp với người dùng | Hiển thị dữ liệu, nhận input | Controller, View |
| Business Logic | Xử lý nghiệp vụ          | Áp dụng quy tắc nghiệp vụ    | Service, Manager |
| Data Access    | Làm việc với DB          | CRUD, kết nối dữ liệu        | Repository, DAO  |

## 8. Ưu và Nhược điểm

### ✅ Ưu điểm:

- **Dễ bảo trì:** Sửa một tầng không ảnh hưởng tầng khác.
- **Dễ mở rộng:** Thêm chức năng mà không phá vỡ cấu trúc.
- **Tăng bảo mật:** Chỉ tầng nghiệp vụ truy cập dữ liệu.
- **Tái sử dụng cao:** Tầng nghiệp vụ dùng cho web, mobile,…

### ⚠️ Nhược điểm:

- Phức tạp hơn với dự án nhỏ.
- Cần hiểu rõ cách tầng giao tiếp.
- Nếu thiết kế sai có thể “rối tầng” (business lẫn presentation).

# Lesson 3: Quy trình thiết kế module & package chức năng

## 1. Tầm quan trọng

- Hệ thống phần mềm thường gồm **nhiều chức năng, module, và lớp**.
- Nếu không có quy trình thiết kế rõ ràng → mã nguồn dễ **rối, chồng chéo, khó bảo trì**.
- Thiết kế module & package giúp:
  - Chia hệ thống thành phần hợp lý.
  - Tổ chức mã nguồn rõ ràng, nhất quán.
  - Dễ mở rộng, bảo trì và tái sử dụng.

## 2. Liên hệ thực tế

- Ví dụ: Hệ thống bán hàng gồm `Product`, `Customer`, `Order`, `Payment`...  
  Nếu đặt chung một nơi → khó quản lý và dễ lỗi.  
  → Cần chia thành **module** và **package** riêng biệt.

## 3. Khái niệm

### Module

- **Định nghĩa:** Nhóm chức năng độc lập, đảm nhận một nhiệm vụ cụ thể.
- **Đặc điểm:**
  - Có mục đích rõ ràng.
  - Tách biệt và có thể tái sử dụng.
  - Chứa nhiều lớp hoặc component cùng hướng đến một mục tiêu.
- **Ví dụ:** `User`, `Product`, `Order`, `Payment`.

### Package

- **Định nghĩa:** Cách tổ chức, nhóm các lớp, interface, hoặc thành phần trong module.
- **Đặc điểm:**
  - Giúp mã nguồn rõ ràng, dễ quản lý.
  - Trong Java, mỗi package tương ứng với **thư mục** trong dự án.
- **Ví dụ:**  
  com.shop.user.controller
  com.shop.user.service
  com.shop.user.repository

  → Mỗi package thể hiện một nhóm chức năng nhỏ trong module `user`.

## 4. Quy trình thiết kế Module & Package

### **Bước 1: Phân tích yêu cầu**

- Đọc kỹ tài liệu SRS, liệt kê các use case chính.
- Xác định các nhóm chức năng độc lập.
- Ví dụ

  | Chức năng          | Module  |
  | ------------------ | ------- |
  | Quản lý người dùng | user    |
  | Quản lý sản phẩm   | product |
  | Đơn hàng           | order   |
  | Thanh toán         | payment |

### **Bước 2: Xác định module**

- Mỗi nhóm chức năng → một module riêng.
- Đặt tên ngắn gọn, phản ánh nghiệp vụ chính.

Ví dụ:  
`user`, `product`, `order`, `payment`.

### **Bước 3: Thiết kế package bên trong module**

**Ví dụ cấu trúc thư mục/package:**

```plaintext
product/
├── controller/
├── service/
├── repository/
├── dto/
└── model/
```

- Cấu trúc này giúp dễ dàng **kiểm thử, bảo trì, mở rộng** mà không ảnh hưởng các module khác.

### **Bước 4: Xác định mối quan hệ giữa module**

- Giao tiếp qua **interface hoặc service**.
- Không phụ thuộc trực tiếp vào logic nội bộ module khác.
- **Nguyên tắc:** “Low coupling – High cohesion”.  
  → Ví dụ: `OrderService` gọi `ProductService`, không truy cập trực tiếp `ProductRepository`.

### **Bước 5: Vẽ sơ đồ kiến trúc module**

Biểu diễn các module và mối quan hệ giữa chúng (qua service hoặc API).

## 5. Ví dụ minh họa

**Module quản lý sản phẩm (Product Module):**

```plaintext
product/
├── controller/
├── service/
├── repository/
├── dto/
└── model/
```

Các class như `ProductController`, `ProductService`, `ProductRepository` hoạt động phối hợp theo kiến trúc 3 tầng.

## 6. So sánh Module & Package

| Tiêu chí    | Module                 | Package               |
| ----------- | ---------------------- | --------------------- |
| Mục đích    | Nhóm chức năng độc lập | Nhóm lớp trong module |
| Mức độ      | Cấp cao hơn (logic)    | Cấp thấp hơn (vật lý) |
| Ví dụ       | user, product, order   | com.shop.user.service |
| Giao tiếp   | Qua interface, API     | Nội bộ module         |
| Tái sử dụng | Dùng cho nhiều dự án   | Trong cùng dự án      |

# Lesson 4: Quy trình thiết kế lớp mở rộng theo kiến trúc 3 tầng

## 1. Tầm quan trọng

- Sau khi hiểu kiến trúc **3 tầng**, bước kế tiếp là **thiết kế lớp cho từng tầng**.
- Thiết kế lớp đúng chuẩn giúp:
  - **Dễ mở rộng** khi có yêu cầu mới.
  - **Tăng khả năng tái sử dụng** và giảm lỗi khi bảo trì.
  - **Phân rõ trách nhiệm** giữa các tầng, giúp code rõ ràng, dễ quản lý.

---

## 2. Liên hệ thực tế

- Ví dụ: hệ thống quản lý sản phẩm.  
  Nếu trộn cả **giao diện**, **logic**, và **truy xuất dữ liệu** trong một file → code sẽ rối.  
  Thiết kế theo **3 tầng (Presentation – Business – Data Access)** giúp tách biệt rõ ràng giữa hiển thị, xử lý và lưu trữ dữ liệu.

---

## 3. Ôn tập kiến trúc 3 tầng

| Tầng                     | Vai trò chính                      | Ví dụ      |
| ------------------------ | ---------------------------------- | ---------- |
| **Presentation Layer**   | Giao tiếp với người dùng (UI, API) | Controller |
| **Business Logic Layer** | Xử lý nghiệp vụ, điều phối dữ liệu | Service    |
| **Data Access Layer**    | Làm việc với CSDL (ORM, DAO)       | Repository |

➡️ Giúp thay đổi dễ dàng — ví dụ, đổi CSDL MySQL → PostgreSQL chỉ cần sửa Data Layer.

---

## 4. Khái niệm “Thiết kế lớp mở rộng”

Là việc **tạo các lớp cho từng tầng** sao cho có thể **kế thừa, mở rộng, tái sử dụng** mà **không làm thay đổi logic cốt lõi**.

---

## 5. Quy trình 5 bước thiết kế lớp mở rộng

### **Bước 1: Xác định đối tượng nghiệp vụ (Business Object)**

- Dựa vào yêu cầu hệ thống → xác định các đối tượng chính (Product, User, Order,...).
- Mỗi đối tượng có:
  - **Entity class** (ở Data Layer)
  - **Service class** (ở Business Layer)

**Ví dụ:**  
`ProductEntity`, `CategoryEntity` (Data)  
`ProductService`, `CategoryService` (Business)

---

### **Bước 2: Thiết kế lớp tầng Data Access**

- Làm việc trực tiếp với CSDL.
- Thường kế thừa từ **BaseRepository** hoặc **DAO**.
- Thực hiện các thao tác **CRUD (Create, Read, Update, Delete)**.  
  **Ví dụ:**

```java
public class ProductRepository extends BaseRepository<Product> {
   // Thao tác CRUD cho Product
}
```

### Bước 3: Thiết kế lớp tầng Business Logic

- Xử lý toàn bộ logic nghiệp vụ, như kiểm tra dữ liệu, tính toán, khuyến mãi,...

- Gọi đến tầng Data khi cần truy xuất/lưu dữ liệu.

- Thường kế thừa từ BaseService để dễ mở rộng.

**Ví dụ:**

```java
public class ProductService extends BaseService<Product> {
public boolean validatePrice(Product p) {
return p.getPrice() > 0;
  }
}
```

### Bước 4: Thiết kế lớp tầng Presentation

- Nhận yêu cầu từ người dùng (qua API hoặc giao diện).

- Gọi sang Service để xử lý nghiệp vụ.

- Trả kết quả về client.

Không chứa logic xử lý hay truy cập DB.

**Ví dụ:**

```java
@RestController
public class ProductController {
   private ProductService service;

   @PostMapping("/create")
   public ResponseEntity<?> create(@RequestBody Product p) {
      return ResponseEntity.ok(service.save(p));
   }
}

```

### Bước 5: Tạo lớp cơ sở (Base Class)

Để tránh lặp code, tạo các lớp cha dùng chung:

| Lớp cơ sở          | Vai trò                                                     |
| ------------------ | ----------------------------------------------------------- |
| **BaseEntity**     | Chứa thuộc tính chung (`id`, `createdDate`, `modifiedDate`) |
| **BaseRepository** | Định nghĩa CRUD cơ bản                                      |
| **BaseService**    | Chứa phương thức dùng chung (`findById`, `findAll`,...)     |

### 6. So sánh các tầng

| Tầng           | Chức năng            | Ví dụ lớp         | Giao tiếp với  |
| -------------- | -------------------- | ----------------- | -------------- |
| Presentation   | Giao tiếp người dùng | ProductController | Business Layer |
| Business Logic | Xử lý nghiệp vụ      | ProductService    | Data Layer     |
| Data Access    | Truy cập CSDL        | ProductRepository | Database       |

### 7. Nguyên tắc SOLID trong thiết kế lớp

S – Single Responsibility: mỗi lớp chỉ làm một việc.

O – Open/Closed: dễ mở rộng, hạn chế sửa đổi.

L – Liskov Substitution: lớp con thay thế được lớp cha.

I – Interface Segregation: interface tách gọn, dễ dùng.

D – Dependency Inversion: tầng trên phụ thuộc abstraction, không phụ thuộc tầng dưới.
