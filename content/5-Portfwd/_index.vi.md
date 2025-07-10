---
title : "Kiểm tra website, fix lỗi CORS & 404"
date: 2025-05-25 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

## 5. Kiểm tra website và xử lý lỗi thường gặp

Sau khi bạn đã triển khai website lên S3 và cấu hình CloudFront thành công, bước tiếp theo là kiểm tra xem website hoạt động ổn định chưa, và xử lý một số lỗi phổ biến như:
{{% notice warning %}}
  Trắng trang (blank page)
{{% /notice %}}
{{% notice warning %}}
  Lỗi 403 hoặc 404
{{% /notice %}}
{{% notice warning %}}
  Lỗi CORS khi gọi API hoặc load tài nguyên
{{% /notice %}}

---

### 🔍 5.1 Truy cập đường dẫn CloudFront

Sau khi tạo thành công Distribution, bạn sẽ có một đường dẫn dạng:

```
https://dxxxxxxxxxxxxxx.cloudfront.net
```

➡️ Mở link này trong trình duyệt để kiểm tra website.

---

### ✅ 5.2 Kiểm tra trang có hiển thị bình thường không

| Trạng thái               | Ý nghĩa                                 |
|--------------------------|------------------------------------------|
| ✅ Hiển thị đúng          | Web hoạt động tốt, không cần xử lý gì     |
| ❌ Trắng trang hoặc lỗi 403 | Có thể do thiếu `index.html` hoặc sai root |
| ❌ Lỗi 404 cho ảnh/CSS   | Có thể upload sai vị trí trong bucket     |

---

### 🧪 5.3 Một số lỗi thường gặp & cách xử lý

---

#### ❗ Lỗi trắng trang hoặc `403 Forbidden`

**Nguyên nhân phổ biến:**
- CloudFront không tìm thấy `index.html`
- Bạn chưa cấu hình `Default root object` trong CloudFront

**Cách xử lý:**
1. Vào CloudFront → Chọn distribution
2. Tab **General** → nhấn **Edit**
3. Điền vào mục **Default root object**:  
index.html
4. Nhấn Save → Đợi 1–2 phút → F5 lại web

---

#### ❗ Lỗi `404 Not Found`

**Nguyên nhân phổ biến:**
- Bạn upload **cả thư mục `build/`** thay vì chỉ nội dung bên trong
- File bị thiếu hoặc sai đường dẫn

**Cách xử lý:**
- Vào bucket S3 → Kiểm tra file có đúng nằm ở root không
  - Đúng: `/index.html`, `/static/js/...`
  - Sai: `/build/index.html` ❌
- Nếu sai → Xoá và upload lại đúng nội dung bên trong `build/`

---

#### ❗ Lỗi CORS (Cross-Origin Resource Sharing)

**Nguyên nhân:**
- Trình duyệt chặn khi web gọi API từ domain khác mà chưa bật CORS

**Cách xử lý (cơ bản với S3):**
1. Vào bucket S3
2. Tab **Permissions** → **CORS configuration**
3. Thêm cấu hình đơn giản sau:

```xml
<CORSConfiguration>
  <CORSRule>
    <AllowedOrigin>*</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
    <AllowedHeader>*</AllowedHeader>
  </CORSRule>
</CORSConfiguration>
```
{{% notice warning %}}
  Đây là cấu hình mở hoàn toàn (dùng trong workshop). Khi triển khai thực tế nên giới hạn domain.
{{% /notice %}}
🧪 Gợi ý kiểm tra web sau khi deploy

| Mục cần kiểm tra         | Có gì bất thường không?                |
|-------------------------|-----------------------------------------|
| Web có hiển thị không?  | Nếu không → kiểm tra index.html         |
| Link CSS/JS có lỗi?     | Kiểm tra tab Network                    |
| Console có lỗi đỏ?      | Kiểm tra tab Console                    |
| Web có ổ khoá HTTPS?    | Nếu chưa → kiểm tra CloudFront          |