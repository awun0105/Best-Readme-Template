<!-- 
BẢN MẪU THIẾT LẬP PRODUCTION (PHỔ QUÁT)
======================================
Trọng tâm: Hướng dẫn chuẩn từng bước cho bất kỳ quy trình triển khai thực tế nào.

GIAO THỨC THỰC THI CHO AGENT:
1. Quét các tệp tự động hóa build và triển khai của dự án.
2. Giải quyết các dấu ngoặc vuông [ ] bằng các nhãn nền tảng và công cụ liên quan.
3. Làm sạch các ghi chú hướng dẫn.
-->

# Thiết lập Production

Hướng dẫn này cung cấp một quy trình chuẩn để triển khai **[Tên Dự án]** vào môi trường vận hành thực tế.

## 1. Yêu cầu Hệ thống
- **Runtime**: [ví dụ: Docker, Node.js, Python runtime]
- **Phần cứng**: [Liên kết đến Yêu cầu Phần cứng trong README]
- **Mạng**: [ví dụ: Mở cổng cho HTTP/HTTPS, cấu hình VPC]

## 2. Chuẩn bị Hạ tầng
*Hướng dẫn thiết lập các máy chủ cần thiết, cơ sở dữ liệu được quản lý, hoặc các tài nguyên đám mây.*

## 3. Cấu hình & Bí mật (Secrets)
1.  Khởi tạo tệp môi trường production (`[ví dụ: .env.production]`).
2.  Điền tất cả các thông tin xác thực nhạy cảm (API keys, mật khẩu DB) vào trình quản lý bí mật bảo mật hoặc tệp môi trường.

## 4. Thực thi / Triển khai
*Hướng dẫn xây dựng và khởi chạy ứng dụng.*

```bash
# Ví dụ lệnh triển khai
[ví dụ: docker-compose up -d]
```

## 5. Kiểm tra Sức khỏe & Xác minh
*Các bước chi tiết để xác minh hệ thống hoạt động hoàn hảo sau khi triển khai.*

---

<div align="center">

[Quay lại Danh mục Tài liệu](../README.md)

</div>
