<!-- 
BẢN MẪU THIẾT LẬP PRODUCTION
============================
Trọng tâm: Hướng dẫn từng bước để triển khai môi trường thực tế.

GIAO THỨC THỰC THI CHO AGENT:
1. Quét các cấu hình triển khai (Docker Compose, Helm, K8s).
2. Điền dữ liệu vào dấu ngoặc vuông [ ].
3. Làm sạch các ghi chú hướng dẫn.
-->

# Thiết lập Production

Hướng dẫn này chi tiết các bước để triển khai **[Tên Dự án]** trong môi trường vận hành thực tế.

## 1. Chuẩn bị Môi trường
*Liệt kê yêu cầu hệ điều hành, trình chạy container và cấu hình mạng.*

## 2. Thiết lập Hạ tầng
*Hướng dẫn thiết lập các phụ thuộc bên ngoài (cơ sở dữ liệu, lưu trữ đối tượng).*

## 3. Cấu hình
1.  Sao chép `.env.production.example` thành `.env.production`.
2.  Cập nhật tất cả các biến nhạy cảm (secrets, keys).

## 4. Triển khai
```bash
# Ví dụ cho Docker Compose
docker-compose -f docker-compose.prod.yml up -d
```

## 5. Xác minh sau Triển khai
*Các bước đảm bảo dịch vụ hoạt động bình thường và có thể truy cập.*

---

<div align="center">

[Quay lại Danh mục Tài liệu](../README.md)

</div>
