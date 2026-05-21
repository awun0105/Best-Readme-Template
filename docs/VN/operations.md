<!-- 
BẢN MẪU VẬN HÀNH
================
Trọng tâm: Trạng thái hệ thống, số liệu, logs, jobs và quản lý sự cố.

GIAO THỨC THỰC THI CHO AGENT:
1. Xác định các endpoint sức khỏe, định dạng log và job backend.
2. Điền dữ liệu vào dấu ngoặc vuông [ ].
3. Làm sạch các ghi chú hướng dẫn.
-->

# Vận hành

Tài liệu này cung cấp hướng dẫn bảo trì và giám sát **[Tên Dự án]** trong môi trường triển khai thực tế.

## Giám sát Sức khỏe

- Endpoint: `[ví dụ: /health]`
- Các hạng mục kiểm tra: [ví dụ: Kết nối cơ sở dữ liệu, trạng thái mô hình, sức khỏe lưu trữ].

## Số liệu (Metrics)

- Endpoint: `[ví dụ: /metrics]`
- Công cụ: [ví dụ: Prometheus / Grafana].
- Các số liệu chính:
  - `[Số liệu 1]`: [Mô tả]
  - `[Số liệu 2]`: [Mô tả]

## Ghi nhật ký (Logging)

- Định dạng: [ví dụ: JSON cấu trúc, Văn bản thuần].
- Cấp độ mặc định: [ví dụ: INFO, DEBUG].

## Các tác vụ nền (Background Jobs)

- Hệ thống: [ví dụ: Redis/RQ, Celery, Cron].
- Các tác vụ đang hoạt động: [Danh sách các tác vụ quan trọng chạy ngầm].

## Quản lý Sự cố

*Hướng dẫn xử lý nhanh các vấn đề thường gặp (ví dụ: mất kết nối DB, đầy ổ cứng).*

---

<div align="center">

[Quay lại Danh mục Tài liệu](README.md)

</div>
