---
title : "Build project React"
date: 2025-05-25 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

## Build project React

Trong phần này, bạn sẽ **sử dụng một project React đã được cung cấp sẵn** để tiết kiệm thời gian khởi tạo. Sau khi tải project về, bạn sẽ tiến hành cài đặt, chỉnh sửa, chạy thử và build để sẵn sàng deploy lên Amazon S3.

---

### 🔹 Bước 1: Tải project React

Bạn có thể tải project mẫu từ GitHub hoặc từ file `.zip` được cung cấp:

[📦 Tải file React project (.zip)](../downloads/react-project.zip)

### 🔹 Bước 2: Cài đặt thư viện

Trong thư mục project, chạy lệnh:

```bash
npm install
```

### 🔹 Bước 3: Chỉnh sửa nội dung website

Mở file:

```text
src/App.js
```

→ Chỉnh sửa giao diện, text, hình ảnh,... theo nhu cầu.
→ Đây là phần sẽ hiển thị sau khi bạn deploy.

### 🔹 Bước 4: Kiểm tra website trên máy

Chạy lệnh:

```bash
npm start
```

→ Trình duyệt sẽ tự mở http://localhost:3000
→ Kiểm tra giao diện và nội dung hiển thị.

### 🔹 Bước 5: Build project để deploy

Sau khi chỉnh sửa xong, chạy lệnh:

```bash
npm run build
```

→ Lệnh này sẽ tạo thư mục:

```text
build/
```

📦 Thư mục build/ chứa toàn bộ nội dung web đã sẵn sàng để upload lên Amazon S3.

👉 Tiếp theo: Chuyển sang Bước 3 – Upload nội dung lên S3

---
