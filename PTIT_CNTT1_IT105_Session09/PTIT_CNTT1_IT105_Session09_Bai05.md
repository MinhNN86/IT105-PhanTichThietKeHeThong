# Tình huống 1: Một sinh viên có một mã sinh viên duy nhất
```mermaid
erDiagram
    STUDENT {
        int student_id PK
        string name
    }
    STUDENT_ID {
        int id PK
        int student_id FK
    }

    STUDENT ||--|| STUDENT_ID : ""

```

# Tình huống 2: Một khách hàng có thể đặt nhiều đơn hàng
```mermaid
erDiagram
    CUSTOMER {
        int customer_id PK
        string name
    }

    ORDER {
        int order_id PK
        date order_date
        int customer_id FK
    }

    CUSTOMER ||--o{ ORDER : ""

```

# Tình huống 3: Một sinh viên có thể học nhiều môn học, và mỗi môn học có nhiều sinh viên
```mermaid
erDiagram
    STUDENT {
        int student_id PK
        string name
    }

    COURSE {
        int course_id PK
        string course_name
    }

    ENROLLMENT {
        int enrollment_id PK
        int student_id FK
        int course_id FK
    }

    STUDENT ||--o{ ENROLLMENT : ""
    COURSE ||--o{ ENROLLMENT : ""

```