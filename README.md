# Bài 1-2: CSDL và quan hệ, thiết kế và tạo CSDL

## 1. Tạo CSDL trên MySQL Workbench

### 1.1. Tạo CSDL bằng giao diện MySQL Workbench

Thực hiện tạo một CSDL mới bằng giao diện MySQL Workbench.

Các bước thực hiện:

1. Mở MySQL Workbench và đăng nhập vào MySQL Server.
2. Tại khu vực **SCHEMAS**, chọn chức năng tạo Schema mới.
3. Nhập tên CSDL.
4. Chọn **Apply** để tạo CSDL.
5. Chọn **Apply** một lần nữa để xác nhận.

### Ảnh minh chứng

![Tạo CSDL trên MySQL Workbench](./Tạo%20CSDL%20trên%20MySQL%20Workbrench.png)

### 1.2. Tạo CSDL bằng câu lệnh SQL

Sử dụng cửa sổ **New Query Tab** trên MySQL Workbench và thực hiện câu lệnh:

```sql
CREATE DATABASE `my_database1`;
```

Câu lệnh trên dùng để tạo một cơ sở dữ liệu mới có tên `my_database1`.

---

## 2. Xóa CSDL trên MySQL Workbench

### 2.1. Xóa CSDL bằng giao diện MySQL Workbench

Chọn Schema cần xóa, click chuột phải và chọn **Drop Schema**, sau đó chọn **Drop Now** để xác nhận.

### Ảnh minh chứng

![Xóa CSDL trên MySQL Workbench](./Xoá%20CSDL%20trên%20MySQL%20Workbrench.png)

### 2.2. Xóa CSDL bằng câu lệnh SQL

Sử dụng câu lệnh SQL trên MySQL Workbench:

```sql
DROP DATABASE `my_database1`;
```

Câu lệnh trên dùng để xóa CSDL `my_database1`.

> **Lưu ý:** `DROP DATABASE` sẽ xóa toàn bộ bảng và dữ liệu bên trong CSDL. Vì vậy cần kiểm tra kỹ trước khi thực hiện.

---

## 3. Tạo bảng trên MySQL Workbench

### 3.1. Tạo CSDL `demo`

Sử dụng MySQL Workbench và thực hiện:

```sql
CREATE DATABASE demo;
```

### 3.2. Chọn CSDL `demo`

```sql
USE demo;
```

### 3.3. Tạo bảng `Student`

Bảng `Student` gồm các trường:

| Tên trường | Kiểu dữ liệu   | Ý nghĩa       |
| ---------- | -------------- | ------------- |
| `id`       | `INT`          | Mã sinh viên  |
| `name`     | `VARCHAR(200)` | Tên sinh viên |
| `age`      | `INT`          | Tuổi          |
| `country`  | `VARCHAR(50)`  | Quốc gia      |

Câu lệnh SQL:

```sql
CREATE TABLE Student(
    id INT,
    name VARCHAR(200),
    age INT,
    country VARCHAR(50)
);
```

### Ảnh minh chứng

![Tạo bảng trên MySQL Workbench](./Tạo%20bảng%20trên%20MySQL%20Workbrench.png)

---

## 4. Xây dựng cơ sở dữ liệu quản lý sinh viên

### Mục tiêu

Luyện tập thao tác tạo bảng bằng **giao diện MySQL Workbench**.

Tiếp tục sử dụng CSDL đã được tạo ở bài thực hành trước:

```text
student-management
```

Trong bài này tạo hai bảng:

* `Class`
* `Teacher`

---

### 4.1. Tạo bảng `Class` bằng giao diện MySQL Workbench

#### Bước 1: Chọn CSDL

Mở MySQL Workbench và đăng nhập vào MySQL Server.

Trong khu vực **SCHEMAS**, tìm CSDL:

```text
student-management
```

#### Bước 2: Chọn Create Table

Click chuột phải vào mục **Tables** của CSDL `student-management` và chọn:

```text
Create Table...
```

#### Bước 3: Đặt tên bảng

Nhập tên bảng:

```text
Class
```

#### Bước 4: Khai báo các trường

Thêm các trường:

| Tên trường | Kiểu dữ liệu   |
| ---------- | -------------- |
| `id`       | `INT`          |
| `name`     | `VARCHAR(200)` |

#### Bước 5: Tạo bảng

Sau khi khai báo đầy đủ các trường, chọn **Apply**.

Kiểm tra lại câu lệnh mà MySQL Workbench sinh ra, sau đó chọn **Apply** để xác nhận.

#### Kết quả

Bảng `Class` được tạo thành công trong CSDL `student-management`.

#### Ảnh minh chứng tạo bảng `Class`

![Tạo bảng Class bằng MySQL Workbench](./Tạo%20bảng%20Class%20MySQL%20Workbench.png)

---

### 4.2. Tạo bảng `Teacher` bằng giao diện MySQL Workbench

#### Bước 1: Chọn Create Table

Trong CSDL:

```text
student-management
```

Click chuột phải vào mục **Tables** và chọn
Create Table...
```

#### Bước 2: Đặt tên bảng

Nhập tên bảng:

```text
Teacher
```

#### Bước 3: Khai báo các trường

Thêm các trường:

| Tên trường | Kiểu dữ liệu   |
| ---------- | -------------- |
| `id`       | `INT`          |
| `name`     | `VARCHAR(200)` |
| `age`      | `INT`          |
| `country`  | `VARCHAR(50)`  |

#### Bước 4: Tạo bảng
Kiểm tra lại câu lệnh mà MySQL Workbench sinh ra, sau đó chọn **Apply** để xác nhận.

#### Kết quả

Bảng `Teacher` được tạo thành công trong CSDL `student-management`.

#### Ảnh minh chứng tạo bảng `Teacher`

![Tạo bảng Teacher bằng MySQL Workbench](./Tạo%20bảng%20Teacher%20MySQL%20Workbench.png)

---

### 4.3. Kiểm tra kết quả

Sau khi hoàn thành, CSDL `student-management` có các bảng:

```text
student-management
└── Tables
    ├── Class
    └── Teacher
```

Cấu trúc bảng `Class`:

```text
Class
├── id       INT
└── name     VARCHAR(200)
```

Cấu trúc bảng `Teacher`:

```text
Teacher
├── id        INT
├── name      VARCHAR(200)
├── age       INT
└── country   VARCHAR(50)
```

### Ảnh minh chứng tổng hợp

![Xây dựng cơ sở dữ liệu quản lý sinh viên](./Xây%20dựng%20cơ%20sở%20dữ%20liệu%20quản%20lý%20sinh%20viên.png)

> **Ghi chú:** Hai bảng `Class` và `Teacher` được tạo bằng chức năng **Create Table** trên giao diện MySQL Workbench theo đúng yêu cầu của bài thực hành.

---

## 5. Quản lý đơn đặt hàng

### 5.1. Các thực thể

Hệ thống quản lý đơn đặt hàng gồm các thực thể:

* `DON_VI`: Đơn vị khách hàng
* `HANG`: Hàng hóa
* `NGUOI_DAT`: Người đặt hàng
* `NOI_GIAO`: Nơi giao hàng
* `NGUOI_NHAN`: Người nhận hàng
* `NGUOI_GIAO`: Người giao hàng
* `DON_DAT_HANG`: Đơn đặt hàng
* `CHI_TIET_DON_HANG`: Chi tiết đơn đặt hàng
* `PHIEU_GIAO_HANG`: Phiếu giao hàng
* `CHI_TIET_PHIEU_GIAO`: Chi tiết phiếu giao hàng

---

### 5.2. Khóa chính và khóa ngoại

#### DON_VI

* `MaDV`: Khóa chính
* `TenDV`
* `DiaChi`
* `DienThoai`

#### HANG

* `MaHang`: Khóa chính
* `TenHang`
* `DonViTinh`
* `MoTa`

#### NGUOI_DAT

* `MaND`: Khóa chính
* `HoTenND`
* `MaDV`: Khóa ngoại → `DON_VI(MaDV)`

#### NOI_GIAO

* `MaDDG`: Khóa chính
* `TenNoiGiao`

#### NGUOI_NHAN

* `MaNN`: Khóa chính
* `HoTenNN`
* `MaDV`: Khóa ngoại → `DON_VI(MaDV)`

#### NGUOI_GIAO

* `MaNG`: Khóa chính
* `HoTenNG`

#### DON_DAT_HANG

* `SoDH`: Khóa chính
* `MaDV`: Khóa ngoại → `DON_VI(MaDV)`
* `MaND`: Khóa ngoại → `NGUOI_DAT(MaND)`
* `NgayDat`

#### CHI_TIET_DON_HANG

Khóa chính tổ hợp:

* `SoDH`
* `MaHang`

Khóa ngoại:

* `SoDH` → `DON_DAT_HANG(SoDH)`
* `MaHang` → `HANG(MaHang)`

Thuộc tính:

* `SoLuong`

#### PHIEU_GIAO_HANG

* `SoPG`: Khóa chính
* `SoDH`: Khóa ngoại → `DON_DAT_HANG(SoDH)`
* `MaDDG`: Khóa ngoại → `NOI_GIAO(MaDDG)`
* `MaNN`: Khóa ngoại → `NGUOI_NHAN(MaNN)`
* `MaNG`: Khóa ngoại → `NGUOI_GIAO(MaNG)`
* `NgayGiao`

#### CHI_TIET_PHIEU_GIAO

Khóa chính tổ hợp:

* `SoPG`
* `MaHang`

Khóa ngoại:

* `SoPG` → `PHIEU_GIAO_HANG(SoPG)`
* `MaHang` → `HANG(MaHang)`

Thuộc tính:

* `SoLuong`
* `DonGia`
* `ThanhTien`

---

### 5.3. Sơ đồ ERD

```mermaid
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
        INT SoDH PK
        INT MaHang PK
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
        INT SoPG PK
        INT MaHang PK
        INT SoLuong
        DECIMAL DonGia
        DECIMAL ThanhTien
    }

    DON_VI ||--o{ NGUOI_DAT : "thuoc"

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
```

---

### 5.4. Ảnh ERD

![ERD Quản lý đơn đặt hàng](./Quản%20lý%20đơn%20đặt%20hàng.png)

---
