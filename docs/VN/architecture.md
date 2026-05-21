<!-- 
BẢN MẪU KIẾN TRÚC
=================
Trọng tâm: Xác định dự án được xây dựng NHƯ THẾ NÀO.

GIAO THỨC THỰC THI CHO AGENT:
1. Xác định các dịch vụ, cơ sở dữ liệu và đường truyền giao tiếp.
2. Giải quyết các thành phần trong dấu ngoặc vuông [ ].
3. Làm sạch các ghi chú hướng dẫn.
-->

# Kiến trúc hệ thống

**[Tên Dự án]** là một hệ thống **[ví dụ: dịch vụ Python đơn lẻ với worker chạy ngầm tách biệt]**. Dự án cung cấp **[ví dụ: các API FastAPI và giao diện Gradio]**, sử dụng **[ví dụ: mô hình CLIP đã được tinh chỉnh]** để tạo embedding, lưu trữ vector tại **[ví dụ: Qdrant]**, lưu trữ dữ liệu nhị phân tại **[ví dụ: MinIO]**, và sử dụng **[ví dụ: Redis/RQ]** để quản lý các tác vụ nền bền vững.

## Sơ đồ cấp cao

*Cung cấp cái nhìn tổng quan về cách khách hàng tương tác với các dịch vụ và lưu trữ.*

```mermaid
flowchart TB
    subgraph Clients["Khách hàng"]
        UI["Giao diện người dùng"]
        APIClient["API Client"]
    end

    subgraph API["Ứng dụng chính"]
        Routes["Routes / Controllers"]
        Services["Logic cốt lõi / Dịch vụ"]
    end

    subgraph Storage["Dịch vụ lưu trữ"]
        DB[("Cơ sở dữ liệu chính")]
        Vector[("Kho lưu trữ Vector")]
        Blob[("Lưu trữ đối tượng")]
    end

    UI --> Routes
    APIClient --> Routes
    Routes --> Services
    Services --> DB
    Services --> Vector
    Services --> Blob
```

## Phong cách kiến trúc

**[BẮT BUỘC]**
*Giải thích mẫu thiết kế và chiến lược phân lớp.*

| Lớp | Trách nhiệm |
|---|---|
| **API / UI** | [ví dụ: HTTP routes, xác thực yêu cầu, các thành phần giao diện] |
| **Dịch vụ cốt lõi** | [ví dụ: Logic nghiệp vụ, suy luận mô hình, điều phối hệ thống] |
| **Bộ chuyển đổi lưu trữ** | [ví dụ: Các wrapper cho cơ sở dữ liệu, client lưu trữ đối tượng] |

### Vòng đời đối tượng thực thi (Runtime)

**[TÙY CHỌN / KHUYẾN NGHỊ]**
*Giải thích cách quản lý các đối tượng có trạng thái (clients, models, settings) trong suốt vòng đời của ứng dụng.*

## Trách nhiệm của các thành phần

### [Tên thành phần 1, ví dụ: Ứng dụng FastAPI]
**[BẮT BUỘC]**
*Chi tiết ranh giới và trách nhiệm của thành phần này (ví dụ: xác thực, phân quyền, số liệu).*

### [Tên thành phần 2, ví dụ: Background Worker]
**[TÙY CHỌN]**
*Chi tiết về các tiến trình phụ hoặc tiến trình chạy ngầm.*

## Mô hình triển khai

### Phát triển cục bộ
*Mô tả stack khi làm việc tại máy cá nhân (ví dụ: tiến trình cục bộ + các phụ thuộc chạy bằng Docker).*

### Triển khai thực tế (Production)
*Mô tả cấu trúc triển khai thực tế (ví dụ: stack Docker Compose, Kubernetes pods).*

## Các đánh đổi đã biết (Tradeoffs)

**[KHUYẾN NGHỊ]**
*Ghi nhận các quyết định thiết kế có chủ đích và giới hạn của chúng (ví dụ: "Ưu tiên sự đơn giản thay vì khả năng mở rộng cực hạn").*

---

<div align="center">

[Quay lại Danh mục Tài liệu](README.md)

</div>
