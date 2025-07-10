---
title : "Cấu hình CloudFront và HTTPS"
date: 2025-05-25 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---


## 4. Cấu hình CloudFront và HTTPS

### 🔰 Giới thiệu về CloudFront

**Amazon CloudFront** là một dịch vụ CDN (Content Delivery Network) được cung cấp bởi AWS. Nó giúp phân phối nội dung web đến người dùng trên toàn cầu với tốc độ nhanh, độ trễ thấp và độ tin cậy cao thông qua một mạng lưới các Edge Location của AWS.

CloudFront hoạt động bằng cách **cache nội dung tĩnh** (HTML, CSS, JS, ảnh, video...) từ nguồn gốc (origin) – như Amazon S3 – và phân phối nội dung đó thông qua các server gần người dùng nhất.

---

### 🎯 Lợi ích khi sử dụng CloudFront

- 🚀 **Tăng tốc tải trang** cho người dùng từ mọi quốc gia
- 🔐 **Hỗ trợ HTTPS miễn phí** với chứng chỉ SSL mặc định
- 📉 **Giảm tải cho S3** vì dữ liệu được cache ở các Edge Location
- 🔎 **Bảo vệ website khỏi các truy cập bất thường** thông qua CloudFront Shield (nâng cao)
- 🧾 **Ghi log truy cập** và dễ dàng tích hợp với các công cụ giám sát như CloudWatch
- 💰 **Tiết kiệm chi phí truyền tải** nếu được cấu hình đúng Price Class

---

### 📦 Nội dung bạn sẽ thực hiện trong mục này:

1. **Tạo một CloudFront Distribution** kết nối với bucket S3 đã có
2. Cấu hình CloudFront để:
   - Phân phối nội dung website tĩnh
   - Tự động chuyển hướng HTTP → HTTPS
3. Kiểm tra link public có HTTPS và hoạt động đúng
4. Xử lý một số lỗi thường gặp (nếu có)

---

👉 Sau khi hoàn thành mục này, website của bạn sẽ:
- Có thể truy cập toàn cầu
- Chạy nhanh hơn, bảo mật hơn
- Sẵn sàng để public cho người dùng cuối
