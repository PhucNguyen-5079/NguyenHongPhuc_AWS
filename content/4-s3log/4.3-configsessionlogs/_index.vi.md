---
title : "Xác nhận cấu hình & kiểm tra CloudFront hoạt động"
date: 2025-05-25 
weight : 3 
chapter : false
pre : " <b> 4.3 </b> "
---

### 4.3 Xác nhận cấu hình & kiểm tra CloudFront hoạt động
---

#### 🔹 Bước 5: Review and create
Tại mục này sẽ cho phép bạn kiểm tra lại những mục mà bạn điền trước đó
- Sau khi kiểm tra xong thì nhấn **Create distribution**
- Sau khi hoàn thành, AWS sẽ tự động chuyển bạn đến trang thông tin CloudFront với trạng thái là Deploying.
![Cloud](/images/anh/4.createdistribution.png)
> **Lưu ý:** Vui lòng đợi trạng thái này trong vài phút - tùy thuộc vào số lượng edge location bạn chọn triển khai.

---

#### 🔹 Bước 6: Kiểm tra CloudFront
- Trong giao diện **CloudFront** Chọn **Id**
![Cloud](/images/anh/26.png)
- Tại mục **Distribution domain name**
  - Đảm bảo rằng **CloudFront** đã deploy xong bằng cách xem nội dung ở mục **Last modified**.
  - Chọn ký hiệu *ô vuông* để copy URL.
![Cloud](/images/anh/25.png)
- Bật một tab khác và dán giá trị CloudFront URL vào thanh tìm kiếm rồi nhấn enter.
![Cloud](/images/anh/27.png)
- Chúc mừng bạn đã triển khai thành công CloudFront để phân phối một website tĩnh được host trên S3 mà không cần phải public bucket hay object.
