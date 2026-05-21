<!-- 
BẢN MẪU SAO LƯU VÀ PHỤC HỒI
===========================
Trọng tâm: Bảo tồn trạng thái và quy trình phục hồi sau sự cố.

GIAO THỨC THỰC THI CHO AGENT:
1. Xác định lệnh dump DB và logic sao lưu lưu trữ đối tượng.
2. Điền dữ liệu vào dấu ngoặc vuông [ ].
3. Làm sạch các ghi chú hướng dẫn.
-->

# Sao lưu và Phục hồi

Các quy trình bảo tồn trạng thái và phục hồi sau sự cố cho **[Tên Dự án]**.

## Chiến lược Sao lưu

- **Cơ sở dữ liệu**: [ví dụ: pg_dump hàng ngày].
- **Lưu trữ đối tượng**: [ví dụ: rclone sync sang S3].
- **Cấu hình**: [ví dụ: Lưu trữ bí mật đã mã hóa].

## Kiểm tra Phục hồi

### 1. Phục hồi Cơ sở dữ liệu
```bash
# Ví dụ lệnh thực hiện
psql -U [user] [tên_db] < backup.sql
```

### 2. Phục hồi Lưu trữ đối tượng
*Hướng dẫn khôi phục các tệp tin/dữ liệu nhị phân.*

## Kiểm tra Tự động
*Giải thích các script hoặc cron jobs dùng để xác minh tính toàn vẹn của bản sao lưu.*

---

<div align="center">

[Quay lại Danh mục Tài liệu](../README.md)

</div>
