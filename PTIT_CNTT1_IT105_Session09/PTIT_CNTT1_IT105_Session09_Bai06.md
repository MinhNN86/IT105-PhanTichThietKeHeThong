```mermaid
erDiagram
    KHACH_HANG {
        string ma_kh PK
        string ten_khach_hang
        string so_dien_thoai
    }

    HOA_DON {
        string ma_hd PK
        string ma_kh FK
        float tong_tien
    }

    SAN_PHAM {
        string ma_sp PK
        string ten_san_pham
    }

    CHI_TIET_HOA_DON {
        string ma_hd FK
        string ma_sp FK
    }

    KHACH_HANG ||--o{ HOA_DON : ""
    HOA_DON ||--o{ CHI_TIET_HOA_DON : ""
    SAN_PHAM ||--o{ CHI_TIET_HOA_DON : ""

```