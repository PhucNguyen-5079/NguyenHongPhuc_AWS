---
title : "Cấu hình Origin và bảo mật CloudFront"
date: 2025-05-25 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

### 4.2 Cấu hình Origin và bảo mật CloudFront

Tiếp theo bạn cần thiết lập nguồn dữ liệu (origin) — là bucket S3 đã upload web — và các cài đặt bảo mật.

---

#### 🔹 Bước 3: Specify origin
1. Tại mục **Origin type** Chọn **Other**
![Cloud](/images/anh/19.png)
2. Tại mục **Origin** 
- Trong trường **Custom origin** điền link website của **Object URL** ở phần 3
- Trong trường **Origin path - optional**Tại mục **Origin path - optional** để trống
![Cloud](/images/anh/20.png)
3. Tại mục **Setting**
- Trong trường **Origin settings**, chọn **Customize origin settings**
- Trong trường **Protocol**, Chọn **HTTP only**, trong đó **HTTP port** để số 80
![Cloud](/images/anh/21.png)
![Cloud](/images/anh/22.png)
4. Sau đó nhấn **Next**
![Cloud](/images/anh/23.png)
---

#### 🔹 Bước 4: Enable security

- Trong trường **Web Application Firewall (WAF)** chọn **Do not enable security protections**
![Cloud](/images/anh/24.png)
> **Lưu ý:**
> - Vì mục tiêu của workshop này là triển khai website tĩnh đơn giản, nhanh gọn, nên bạn **KHÔNG cần bật WAF** để tránh:
>   - Gây phức tạp không cần thiết
>   - Phát sinh chi phí thêm (WAF có tính phí riêng)
>   - Mất thời gian thiết lập rule, ACLs mà không cần thiết cho web tĩnh

- Sau đó nhấn **Next**

✅ Tiếp theo: sang [4.3 – Review và kiểm tra CloudFront]