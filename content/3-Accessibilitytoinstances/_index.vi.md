---
title : "Tạo bucket S3 và upload nội dung website"
date: 2025-05-25 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

## 3. Tạo bucket S3 và upload nội dung website

Sau khi bạn đã có thư mục `build/` từ project React (hoặc `public/` nếu là Hugo), bạn sẽ tiến hành upload toàn bộ nội dung này lên Amazon S3 để website có thể được truy cập công khai.

---

### 🔹 3.1 Truy cập vào dịch vụ Amazon S3

1. Truy cập: [https://s3.console.aws.amazon.com/s3](https://s3.console.aws.amazon.com/s3)
2. Nhấn nút **Create bucket**
![Cloud](/images/anh/3-s3.png)
3. Điền các thông tin sau:
   - **Bucket name**: tên duy nhất toàn cầu, ví dụ: `phuccg-react-web`
   - **Object Ownership**: chọn ACLs disabled (recommended)
![Cloud](/images/anh/1.png)
4. Ở phần **Block Public Access**, hãy **bỏ chọn dòng "Block all public access"**
5. Xác nhận cảnh báo → tích ✅ vào ô xác nhận
![Cloud](/images/anh/3.s3.block.png)
6. Nhấn **Create bucket**
![Cloud](/images/anh/3.s3create.png)

---

### 🔹 3.2 Upload nội dung web vào bucket

1. Vào bucket vừa tạo
![Cloud](/images/anh/3.s3taoxong.png)
2. Nhấn **Upload**
![Cloud](/images/anh/2.png)
3. Chọn toàn bộ nội dung bên trong thư mục `build/`
{{% notice note %}}
 **KHÔNG upload cả thư mục `build`**, chỉ các file bên trong
{{% /notice %}}
![Cloud](/images/anh/3.png)
4. Nhấn **Upload**
![Cloud](/images/anh/4.png)

---

### 🔹 3.3 Cấp quyền public cho các file

1. Chọn tất cả file vừa upload → Nhấn **Actions > Make public**
2. Xác nhận khi được hỏi
{{% notice note %}}
 Hoặc bạn có thể dùng Bucket Policy ở bước tiếp theo để public toàn bộ.
{{% /notice %}}

---

### 🔹 3.4 Bật Static website hosting

1. Trong bucket, vào tab **Properties**
2. Kéo xuống mục **Static website hosting**
3. Nhấn **Edit**, rồi bật:
![Cloud](/images/anh/5.png)
   - Enable → ✅ `Enable`
   - **Index document**: `index.html`
   - **Error document**: `index.html` (hoặc `error.html` nếu có)
   ![Cloud](/images/anh/6.png)
4. Nhấn **Save changes**
![Cloud](/images/anh/7.png)
---

### ✅ Kết quả

Bạn sẽ thấy một đường dẫn như sau:

```plaintext
http://phuccg-react-web.s3-website-ap-southeast-1.amazonaws.com
```
![Cloud](/images/anh/8.png)
---

### 🔹 3.5 Cấp quyền public cho file

1. Trong bucket, vào tab **Permissions**
![Cloud](/images/anh/9.png)
2. Chọn **Bucket policy**
3. Nhấn **Edit**, rồi dán đoạn Json này vào:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicRead",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::phuccg-react-web/*"
    }
  ]
}
```
![Cloud](/images/anh/10.png)
![Cloud](/images/anh/11.png)
👉Thay **phuccg-react-web** bằng đúng tên bucket của bạn.

4. Nhấn **Save changes**
![Cloud](/images/anh/12.png)
---

### 🔹 3.6 Kiểm tra website

Sau khi đã làm xong các bước thì tới bước tiếp theo sẽ là kiểm tra website
1. Trong bucket, vào tab **Objects**
2. Chọn thư mục **phuccg-react-web** đã tải lên
3. Chọn file **index.html**
![Cloud](/images/anh/13.png)
4. Tìm thông tin chi tiết của **index.html**
5. Chọn **Object URL**.
![Cloud](/images/anh/14.png)
6. Mở URL trong tab mới của trình duyệt
![Cloud](/images/anh/15.png)
