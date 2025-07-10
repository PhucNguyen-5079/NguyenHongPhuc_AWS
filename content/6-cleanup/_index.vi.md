---
title : "Dọn dẹp tài nguyên  "
date : 2021
weight : 6
chapter : false
pre : "<b>6. </b>"
---

## 6. Dọn dẹp tài nguyên

Sau khi hoàn tất quá trình thực hành và xác nhận website hoạt động thành công, bạn nên **xóa các tài nguyên đã tạo trong workshop** để tránh phát sinh chi phí không cần thiết trên AWS.

---

### 🧹 6.1 Xoá CloudFront Distribution
{{% notice warning %}}
 CloudFront không thể xóa ngay. Bạn cần disable (tắt) trước rồi chờ trạng thái chuyển sang `Deployed`.
{{% /notice %}}

#### Các bước:

1. Truy cập [CloudFront Console](https://console.aws.amazon.com/cloudfront)
2. Chọn Distribution bạn đã tạo
3. Nhấn **Disable** → xác nhận
![Cloud](/images/anh/28.png)
![Cloud](/images/anh/29.png)
4. Đợi trạng thái chuyển từ `Enabled` → `Disabled`
![Cloud](/images/anh/30.png)
5. Sau đó nhấn **Delete**
{{% notice note %}}
 *Việc này có thể mất vài phút để CloudFront thực hiện xong.*
{{% /notice %}}
---

### 🧹 6.2 Xoá Bucket S3

1. Truy cập [S3 Console](https://s3.console.aws.amazon.com/s3)
2. Chọn bucket bạn đã tạo (VD: `phuccg-react-web`)
3. Nhấn **Empty** để xóa toàn bộ nội dung
![Cloud](/images/anh/31.png)
![Cloud](/images/anh/32.png)
![Cloud](/images/anh/33.png)
4. Sau đó nhấn **Delete bucket** → gõ tên bucket để xác nhận
![Cloud](/images/anh/34.png)
![Cloud](/images/anh/35.png)
![Cloud](/images/anh/36.png)
{{% notice warning %}}
Bạn **phải empty trước** thì mới có thể delete bucket.
{{% /notice %}}
---

### 🧹 6.3 Kiểm tra các tài nguyên còn tồn tại

| Dịch vụ             | Việc cần làm                    |
|---------------------|----------------------------------|
| **S3**              | Đảm bảo không còn bucket dư thừa |
| **CloudFront**      | Tất cả distribution đã xóa       |
| **ACM (chứng chỉ SSL)** | Nếu có dùng domain riêng → có thể xoá thủ công |
| **IAM Role / OAC**  | Không cần xoá nếu không tạo thủ công |
| **Route 53 (nếu có)**| Nếu bạn gắn domain → kiểm tra domain zone |

---

### ✅ Hoàn tất

Chúc mừng bạn đã hoàn tất workshop triển khai website tĩnh bằng **Amazon S3 và CloudFront**!

Bạn đã học được cách:
- Build project React
- Upload nội dung lên S3
- Cấu hình CDN và HTTPS với CloudFront
- Kiểm tra, xử lý lỗi và dọn dẹp tài nguyên AWS

---

👉 Có thể tiếp tục học:
- Tự động hoá deploy bằng GitHub Actions
- Gắn domain riêng với Route 53
- Kết hợp API backend bằng Lambda hoặc Amplify

