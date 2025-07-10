---
title : "**Tạo một CloudFront Distribution** kết nối với bucket S3 đã có"
date: 2025-05-25 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

### 4.1 Truy cập vào CloudFront và tạo mới Distribution

Để phân phối nội dung web qua CloudFront, bạn cần tạo một **CloudFront Distribution** mới và trỏ nó về bucket S3 chứa website của bạn.

---

#### 🔹 Bước 1: Truy cập dịch vụ CloudFront

1. Truy cập đường dẫn:  
   👉 [https://console.aws.amazon.com/cloudfront/v3/home](https://console.aws.amazon.com/cloudfront/v3/home)
2. Tại trang CloudFront, nhấn nút **Create distribution**
![Cloud](/images/anh/16.png)
---

#### 🔹 Bước 2: Get started

- Tại mục **Distribution options**:

  - Điền tên tại mục **Distribution name**, ví dụ: `react-app-cdn1`
  - Trong trường **Description - optional** có thể bỏ trống
  - Chọn **Single website or app**
  ![Cloud](/images/anh/17.png)
  - Tại mục **Custom domain - optional** có thể bỏ trống
  - Sau đó nhấn **Next**
  ![Cloud](/images/anh/18.png)
✅ Tiếp theo: sang [4.2 – Cấu hình Origin & Security]

