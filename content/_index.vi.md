---
title : "Session Management"
date: 2025-05-25 
weight : 1 
chapter : false
---
# Workshop: Triển khai Website tĩnh với Amazon S3 và CloudFront

### Tổng quan

Trong workshop này, bạn sẽ tìm hiểu cách sử dụng các dịch vụ của AWS để triển khai một website tĩnh (static website) được build bằng React hoặc Hugo.  
Bạn sẽ thực hành:
- Tải mã nguồn lên dịch vụ Amazon S3
- Phân phối nội dung toàn cầu thông qua Amazon CloudFront (CDN)
- Bật HTTPS để tăng bảo mật
- Quản lý quyền truy cập và chính sách S3 để website hoạt động ổn định.

![CloudFrontFlow](/images/arc-log.png)

---

### Nội dung

1. [Giới thiệu về hosting web tĩnh trên AWS](1-introduce/)
2. [Chuẩn bị project (React) và build](2-project-setup/)
3. [Tạo bucket S3 và upload nội dung website](3-upload-s3/)
4. [Cấu hình CloudFront và HTTPS](4-cloudfront-https/)
5. [Kiểm tra website, fix lỗi CORS & 404](5-troubleshoot/)
6. [Dọn dẹp tài nguyên](6-cleanup/)
