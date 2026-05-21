<!-- 
BẢN MẪU PHÁT TRIỂN CỤC BỘ
=========================
Trọng tâm: Thiết lập mã nguồn để làm việc và gỡ lỗi tại máy cá nhân.

GIAO THỨC THỰC THI CHO AGENT:
1. Xác định công cụ phát triển, lệnh kiểm thử và các bước thiết lập.
2. Điền dữ liệu vào dấu ngoặc vuông [ ].
3. Làm sạch các ghi chú hướng dẫn.
-->

# Phát triển Cục bộ

Hướng dẫn này giải thích cách thiết lập **[Tên Dự án]** để phát triển, kiểm thử và gỡ lỗi tại máy cá nhân.

## 1. Điều kiện tiên quyết
- [ví dụ: Python 3.11+, Node.js 18+]
- [ví dụ: Công cụ quản lý môi trường ảo: venv, uv, hoặc conda]

## 2. Các bước thiết lập
1.  **Môi trường**: Tạo và kích hoạt môi trường ảo.
2.  **Thư viện**: Cài đặt các thư viện phụ thuộc cho phát triển.
    ```bash
    [ví dụ: pip install -r requirements-dev.txt]
    ```
3.  **Dịch vụ cục bộ**: Khởi chạy hạ tầng cục bộ (ví dụ: qua `docker-compose.dev.yml`).

## 3. Chạy ứng dụng tại máy cá nhân
*Hướng dẫn chạy server hoặc tiến trình chính trong chế độ debug.*

## 4. Kiểm thử (Testing)
*Các lệnh để chạy unit test và integration test.*

## 5. Linting và Định dạng
*Hướng dẫn sử dụng các công cụ như Ruff, ESLint, hoặc Prettier.*

---

<div align="center">

[Quay lại Danh mục Tài liệu](README.md)

</div>
