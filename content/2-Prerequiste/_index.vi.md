---
title : "Chuẩn bị project (React) và build"
date: 2025-05-25 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}
Trước khi bắt đầu workshop này, bạn cần chuẩn bị một website tĩnh được build từ các framework phổ biến như **React**, **Vue**, **Hugo**, hoặc **Jekyll**. Trong phần này, chúng ta sẽ tập trung vào React.
{{% /notice %}}

Trong bài thực hành này, bạn sẽ triển khai website tĩnh lên AWS bằng cách sử dụng hai dịch vụ chính:
- **Amazon S3** để lưu trữ và phục vụ nội dung website
- **Amazon CloudFront** để phân phối nội dung toàn cầu với hiệu suất cao và hỗ trợ HTTPS miễn phí

---

Để bắt đầu, bạn cần thực hiện các bước sau:

### 2.1 Chuẩn bị môi trường phát triển
- Cài đặt Node.js và npm
- Cài đặt `create-react-app` để khởi tạo project React
- Tạo thư mục và kiểm tra giao diện web trên localhost

### 2.2 Build project React để deploy
- Tuỳ chỉnh nội dung web trong `src/`
- Chạy lệnh `npm run build` để tạo thư mục `build/` chứa nội dung sẵn sàng deploy

---

Nếu bạn chưa quen với React hoặc chưa biết cách tạo project, có thể tham khảo tài liệu sau:
- [Hướng dẫn React chính thức](https://reactjs.org/docs/getting-started.html)
{{% notice note %}}
 Sau khi hoàn tất bước này, bạn sẽ có thư mục `build/` – đây là nội dung sẽ được upload lên Amazon S3.
{{% /notice %}}
---

### Mục lục phần chuẩn bị:
  - [2.1 Chuẩn bị môi trường phát triển](2.1-setup/)
  - [2.2 Build project React](2.2-build/)
