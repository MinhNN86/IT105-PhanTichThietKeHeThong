```mermaid
classDiagram

%% ===== Presentation Layer =====
class PostController {
  + createPost()
  + editPost()
  + viewPost()
  + deletePost()
}

class CommentController {
  + addComment()
  + editComment()
  + deleteComment()
}

class UserController {
  + register()
  + login()
  + viewProfile()
}

%% ===== Business Logic Layer =====
class PostService {
  + validatePost()
  + publishPost()
  + getPostById()
  + getAllPosts()
}

class CommentService {
  + validateComment()
  + getCommentsByPost()
}

class UserService {
  + createUser()
  + getUser()
  + updateUser()
}

class AuthService {
  + loginUser()
  + authorizeRole()
}

%% ===== Data Access Layer =====
class PostRepository {
  + savePost()
  + findPostById()
  + findAllPosts()
  + deletePost()
}

class CommentRepository {
  + saveComment()
  + findCommentByPostId()
  + deleteComment()
}

class UserRepository {
  + saveUser()
  + findUserById()
  + findUserByUsername()
}

%% ===== Relationships =====
PostController --> PostService : gọi
CommentController --> CommentService : gọi
UserController --> UserService : gọi
UserController --> AuthService : xác thực

PostService --> PostRepository : truy xuất dữ liệu
CommentService --> CommentRepository : truy xuất dữ liệu
UserService --> UserRepository : truy xuất dữ liệu
AuthService --> UserRepository : xác thực

```

## Mô tả vai trò từng module

| **Tầng**           | **Module**          | **Vai trò**                                               |
| ------------------ | ------------------- | --------------------------------------------------------- |
| **Presentation**   | `PostController`    | Nhận yêu cầu từ người dùng về bài viết (tạo, xem, xóa).   |
|                    | `CommentController` | Quản lý bình luận người dùng.                             |
|                    | `UserController`    | Xử lý đăng ký, đăng nhập, hồ sơ người dùng.               |
| **Business Logic** | `PostService`       | Xử lý logic bài viết (kiểm tra nội dung, định dạng, lưu). |
|                    | `CommentService`    | Xử lý logic bình luận (kiểm duyệt, liên kết bài viết).    |
|                    | `UserService`       | Xử lý thông tin người dùng và cập nhật tài khoản.         |
|                    | `AuthService`       | Xác thực người dùng, phân quyền.                          |
| **Data Access**    | `PostRepository`    | Thao tác CRUD với bảng `Posts`.                           |
|                    | `CommentRepository` | Quản lý dữ liệu `Comments`.                               |
|                    | `UserRepository`    | Quản lý dữ liệu người dùng (`Users`).                     |
