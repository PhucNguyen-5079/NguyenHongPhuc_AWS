---
title : "Configure Origin and CloudFront Security"
date: 2025-05-25 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

### 4.2 Configure Origin and CloudFront Security

Next, you need to set up the data source (origin)—which is the S3 bucket you uploaded your website to—and configure security settings.

---

#### 🔹 Step 3: Specify origin
1. In **Origin type** select **Other**
![Cloud](/images/anh/19.png)
2. In **Origin**
   - In the **Custom origin** field, enter the website link from the **Object URL** in step 3
   - Leave **Origin path - optional** blank
![Cloud](/images/anh/20.png)
3. In **Setting**
   - In **Origin settings**, select **Customize origin settings**
   - In **Protocol**, select **HTTP only**, and set **HTTP port** to 80
![Cloud](/images/anh/21.png)
![Cloud](/images/anh/22.png)
4. Then click **Next**
![Cloud](/images/anh/23.png)
---

#### 🔹 Step 4: Enable security

- In **Web Application Firewall (WAF)** select **Do not enable security protections**
![Cloud](/images/anh/24.png)
> **Note:**
> - For the purpose of this workshop, which is to deploy a simple, quick static website, you **do NOT need to enable WAF** to avoid:
>   - Unnecessary complexity
>   - Additional costs (WAF is charged separately)
>   - Time spent setting up rules and ACLs that are not needed for a static site

- Then click **Next**

✅ Next: go to [4.3 – Review and check CloudFront]
