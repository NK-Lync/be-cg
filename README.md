# Bài 1-2: csdl và qh, thiết kế và tạo csdl

## 1. Tạo CSDL trên MySQL Workbench

![Tạo CSDL trên MySQL Workbench](./Tạo%20CSDL%20trên%20MySQL%20Workbrench.png)


## 2. Xóa CSDL trên MySQL Workbench

![Xóa CSDL trên MySQL Workbench](./Xoá%20CSDL%20trên%20MySQL%20Workbrench.png)


## 3. Tạo bảng trên MySQL Workbench

![Tạo bảng trên MySQL Workbench](./Tạo%20bảng%20trên%20MySQL%20Workbrench.png)


## 4. Xây dựng cơ sở dữ liệu quản lý sinh viên

![Xây dựng cơ sở dữ liệu quản lý sinh viên](./Xây%20dựng%20cơ%20sở%20dữ%20liệu%20quản%20lý%20sinh%20viên.png)


## 5. Quản lý đơn đặt hàng

### Sơ đồ ERD

erDiagram
    DON_VI {
        INT MaDV PK
        VARCHAR TenDV
        VARCHAR DiaChi
        VARCHAR DienThoai
    }

    HANG {
        INT MaHang PK
        VARCHAR TenHang
        VARCHAR DonViTinh
        VARCHAR MoTa
    }

    NGUOI_DAT {
        INT MaND PK
        VARCHAR HoTenND
        INT MaDV FK
    }

    NOI_GIAO {
        INT MaDDG PK
        VARCHAR TenNoiGiao
    }

    NGUOI_NHAN {
        INT MaNN PK
        VARCHAR HoTenNN
        INT MaDV FK
    }

    NGUOI_GIAO {
        INT MaNG PK
        VARCHAR HoTenNG
    }

    DON_DAT_HANG {
        INT SoDH PK
        INT MaDV FK
        INT MaND FK
        DATE NgayDat
    }

    CHI_TIET_DON_HANG {
        INT SoDH PK, FK
        INT MaHang PK, FK
        INT SoLuong
    }

    PHIEU_GIAO_HANG {
        INT SoPG PK
        INT SoDH FK
        INT MaDDG FK
        INT MaNN FK
        INT MaNG FK
        DATE NgayGiao
    }

    CHI_TIET_PHIEU_GIAO {
        INT SoPG PK, FK
        INT MaHang PK, FK
        INT SoLuong
        DECIMAL DonGia
        DECIMAL ThanhTien
    }

    DON_VI ||--o{ NGUOI_DAT : "thuoc"
    DON_VI ||--o{ NGUOI_NHAN : "thuoc"

    DON_VI ||--o{ DON_DAT_HANG : "dat"
    NGUOI_DAT ||--o{ DON_DAT_HANG : "lap"

    DON_DAT_HANG ||--|{ CHI_TIET_DON_HANG : "co"
    HANG ||--o{ CHI_TIET_DON_HANG : "duoc_dat"

    DON_DAT_HANG ||--o{ PHIEU_GIAO_HANG : "duoc_giao"

    NOI_GIAO ||--o{ PHIEU_GIAO_HANG : "giao_tai"
    NGUOI_NHAN ||--o{ PHIEU_GIAO_HANG : "nhan"
    NGUOI_GIAO ||--o{ PHIEU_GIAO_HANG : "giao"

    PHIEU_GIAO_HANG ||--|{ CHI_TIET_PHIEU_GIAO : "co"
    HANG ||--o{ CHI_TIET_PHIEU_GIAO : "duoc_giao"

![ERD Quản lý đơn đặt hàng](./Quản%20lý%20đơn%20đặt%20hàng.png)
