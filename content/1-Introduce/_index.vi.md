---
title : "Giới thiệu"
date: 2025-05-25 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
![Cloud](/images/anh/Bangdiagram.drawio.png)
**Amazon S3 và CloudFront** là hai dịch vụ chủ lực của AWS giúp bạn triển khai một **website tĩnh** một cách nhanh chóng, tiết kiệm và bảo mật.  
Bạn không cần quản lý máy chủ, không cần cài đặt Nginx hoặc Apache, và vẫn có thể phân phối website của mình đến người dùng toàn cầu với hiệu suất cao và HTTPS bảo mật.

Khi sử dụng S3 để host website và CloudFront để phân phối nội dung (CDN), bạn sẽ có được những lợi ích sau:

- Không cần thuê máy chủ riêng (EC2) hoặc VPS.
- Không cần cài đặt phần mềm web server như Apache hay Nginx.
- Không cần mở cổng hay cấu hình tường lửa.
- Website có thể được truy cập toàn cầu qua **CloudFront CDN**, tăng tốc độ tải.
- Hỗ trợ **HTTPS miễn phí** thông qua chứng chỉ của CloudFront.
- Có thể kết hợp với tên miền riêng hoặc dùng link mặc định dạng `https://xxxxx.cloudfront.net`.
- S3 hỗ trợ quản lý phiên bản (versioning), public/private access và dễ dàng tích hợp với các dịch vụ khác.
- Triển khai website tĩnh như **React**, **Vue**, **Hugo**, **Jekyll**... cực kỳ đơn giản chỉ với 1 thư mục `build/`.

Với những ưu điểm này, việc sử dụng **S3 + CloudFront** là một lựa chọn tuyệt vời để triển khai các website cá nhân, portfolio, landing page, hoặc thậm chí là các blog tĩnh — mà không cần lo về chi phí máy chủ hoặc bảo mật kết nối.

Bạn không còn cần phải triển khai server EC2 hay Bastion Host để public web — toàn bộ quy trình **hoàn toàn serverless** và có thể **auto scale không giới hạn**.
