---
title : "Create a CloudFront Distribution connected to an existing S3 bucket"
date: 2025-05-25 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

### 4.1 Access CloudFront and create a new Distribution

To distribute web content via CloudFront, you need to create a **CloudFront Distribution** and point it to the S3 bucket containing your website.

---

#### 🔹 Step 1: Access the CloudFront service

1. Go to:  
   👉 [https://console.aws.amazon.com/cloudfront/v3/home](https://console.aws.amazon.com/cloudfront/v3/home)
2. On the CloudFront page, click **Create distribution**
![Cloud](/images/anh/16.png)
---

#### 🔹 Step 2: Get started

- In **Distribution options**:

  - Enter a name in **Distribution name**, e.g., `react-app-cdn1`
  - The **Description - optional** field can be left blank
  - Select **Single website or app**
  ![Cloud](/images/anh/17.png)
  - The **Custom domain - optional** field can be left blank
  - Then click **Next**
  ![Cloud](/images/anh/18.png)
✅ Next: go to [4.2 – Configure Origin & Security]
