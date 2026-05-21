<!-- 
BẢN MẪU VẬN HÀNH
================
Trọng tâm: Trạng thái hệ thống, số liệu, logs, các tác vụ nền và quản lý sự cố.

GIAO THỨC THỰC THI CHO AGENT:
1. Xác định các endpoint sức khỏe, định dạng log và job backend.
2. Điền dữ liệu vào dấu ngoặc vuông [ ].
3. Làm sạch các ghi chú hướng dẫn.
-->

# Hướng dẫn Vận hành

Tài liệu này giải thích cách kiểm tra và vận hành **[Tên Dự án]** sau khi hệ thống đã khởi chạy.

## Giám sát Sức khỏe (Health)

Kiểm tra trạng thái hệ thống thông qua API:

```bash
curl http://localhost:[CỔNG]/health
```

Phản hồi sức khỏe thường bao gồm:
- `status`: Trạng thái tổng quát của API.
- **[Trạng thái Thành phần 1]**: [ví dụ: Kết nối Cơ sở dữ liệu].
- **[Trạng thái Thành phần 2]**: [ví dụ: Trạng thái nạp Mô hình].

*Lưu ý: [Ghi chú tùy chọn về cơ chế lazy-loading hoặc các hành vi khởi động đặc thù].*

## Số liệu (Metrics)

Cung cấp các số liệu định dạng Prometheus để giám sát:

```bash
curl http://localhost:[CỔNG]/metrics
```

**Các nhóm số liệu quan trọng:**

| Số liệu | Ý nghĩa |
|---|---|
| `[Tên Số liệu 1]` | [Mô tả về những gì đang được đo lường/đếm] |
| `[Tên Số liệu 2]` | [Mô tả] |

*Lưu ý về tính khả dụng: Endpoint `/metrics` thường yêu cầu thiết lập `[TÊN_BIẾN_MÔI_TRƯỜNG]=true` để hoạt động.*

## Ghi nhật ký (Logging)

- **Phát triển cục bộ**: Thường sử dụng định dạng `text` để dễ đọc.
- **Triển khai Production**: Khuyến nghị sử dụng định dạng `json` để phục vụ việc cấu trúc hóa và tập hợp log.

**Truy vết yêu cầu (Request Tracking):**
Mỗi yêu cầu được gán một ID duy nhất. Hãy tìm header `X-Request-ID` trong phản hồi để khớp các cuộc gọi API với nhật ký hệ thống tại backend.

## Các tác vụ nền (Background Jobs)

*Nếu dự án sử dụng hàng đợi tác vụ (ví dụ: Redis/RQ, Celery, Cron), hãy tài liệu hóa cách quản lý job tại đây.*

### 1. Khởi tạo một tác vụ
```bash
curl -X POST http://localhost:[CỔNG]/api/v1/[đường-dẫn-job] \
  -H "X-API-Key: $API_KEY" \
  -d '{"param": "value"}'
```

### 2. Giám sát trạng thái
```bash
curl -H "X-API-Key: $API_KEY" \
  http://localhost:[CỔNG]/api/v1/[đường-dẫn-job]/<id_job>
```

**Ý nghĩa các trạng thái:**
- `queued`: Đã tiếp nhận, đang chờ worker.
- `running`: Đang được xử lý.
- `completed`: Thành công.
- `failed`: Thất bại; kiểm tra log để biết chi tiết lỗi.

## Các sự cố thường gặp / Xử lý sự cố

### API trả về lỗi 401 (Unauthorized)
**Nguyên nhân**: API key bị thiếu hoặc không chính xác.
**Kiểm tra**: Đảm bảo biến `[TÊN_BIẾN_MÔI_VAR]` khớp với key được gửi trong header.

### Tác vụ bị kẹt ở trạng thái Queued
**Nguyên nhân**: Tiến trình worker chưa chạy hoặc kết nối sai hàng đợi/cơ sở dữ liệu.
**Xử lý**: Kiểm tra trạng thái container của worker và cấu hình `[TÊN_BIẾN_MÔI_TRƯỜNG]`.

### [Tên vấn đề 3, ví dụ: Phản hồi chậm]
**Nguyên nhân**: [Mô tả].
**Xử lý**: [Các bước gỡ lỗi].

---

<div align="center">

[Quay lại Danh mục Tài liệu](README.md)

</div>
