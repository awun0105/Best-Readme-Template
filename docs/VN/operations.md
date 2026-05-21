<!-- 
BẢN MẪU VẬN HÀNH (PHỔ QUÁT)
==========================
Trọng tâm: Sức khỏe hệ thống, số liệu, nhật ký và quy trình bảo trì.

GIAO THỨC THỰC THI CHO AGENT:
1. Quét dự án để tìm các endpoint giám sát và cấu hình ghi nhật ký.
2. Giải quyết các dấu ngoặc vuông [ ] bằng các giao diện vận hành cụ thể của dự án.
3. Làm sạch các ghi chú hướng dẫn.
-->

# Hướng dẫn Vận hành

Tài liệu này giải thích cách giám sát, kiểm tra và bảo trì **[Tên Dự án]** trong môi trường vận hành thực tế.

## Giám sát Sức khỏe

Truy cập giao diện kiểm tra sức khỏe để xác minh trạng thái hệ thống:

```bash
curl http://[HOST]:[CỔNG]/[đường-dẫn-health]
```

**Các hạng mục kiểm tra:**
- [ví dụ: Kết nối cơ sở dữ liệu]
- [ví dụ: Tính khả dụng của dịch vụ]

## Số liệu Hệ thống (Metrics)

Hiển thị và thu thập các số liệu hiệu năng (ví dụ: qua Prometheus):

```bash
curl http://[HOST]:[CỔNG]/[đường-dẫn-metrics]
```

**Các danh mục số liệu chính:**
- **Lưu lượng**: [ví dụ: Số lượng yêu cầu, thông lượng]
- **Độ trễ**: [ví dụ: Biểu đồ thời gian phản hồi]
- **Lỗi**: [ví dụ: Số lượng lỗi 4xx/5xx]

## Ghi nhật ký & Khả năng giám sát

Mô tả chiến lược ghi nhật ký và cách truy cập nhật ký hệ thống.

- **Định dạng Log chuẩn**: [ví dụ: JSON cấu trúc]
- **Phương thức truy cập**: [ví dụ: `docker logs` hoặc một hệ thống tập hợp log trung tâm]

## Bảo trì Định kỳ

*Hướng dẫn cho các tác vụ theo lịch trình, dọn dẹp dữ liệu hoặc cập nhật hệ thống.*

## Xử lý Sự cố (Cơ bản)

| Sự cố | Kiểm tra ban đầu | Hành động |
|---|---|---|
| **[Vấn đề 1]** | [Bước xác minh] | [Bước giải quyết] |
| **[Vấn đề 2]** | [Bước xác minh] | [Bước giải quyết] |

---

<div align="center">

[Quay lại Danh mục Tài liệu](README.md)

</div>
