---
title : "Clean up resources"
date : 2021
weight : 6
chapter : false
pre : "<b>6. </b>"
---

## 6. Clean up resources

After completing the workshop and confirming your website works, you should **delete all resources created during the workshop** to avoid unnecessary AWS charges.

---

### 🧹 6.1 Delete CloudFront Distribution
{{% notice warning %}}
 CloudFront cannot be deleted immediately. You must disable it first and wait for the status to change to `Deployed`.
{{% /notice %}}

#### Steps:

1. Go to [CloudFront Console](https://console.aws.amazon.com/cloudfront)
2. Select the Distribution you created
3. Click **Disable** → confirm
![Cloud](/images/anh/28.png)
![Cloud](/images/anh/29.png)
4. Wait for the status to change from `Enabled` → `Disabled`
![Cloud](/images/anh/30.png)
5. Then click **Delete**
{{% notice note %}}
 *This may take a few minutes for CloudFront to complete.*
{{% /notice %}}
---

### 🧹 6.2 Delete S3 Bucket

1. Go to [S3 Console](https://s3.console.aws.amazon.com/s3)
2. Select the bucket you created (e.g., `phuccg-react-web`)
3. Click **Empty** to delete all contents
![Cloud](/images/anh/31.png)
![Cloud](/images/anh/32.png)
![Cloud](/images/anh/33.png)
4. Then click **Delete bucket** → type the bucket name to confirm
![Cloud](/images/anh/34.png)
![Cloud](/images/anh/35.png)
![Cloud](/images/anh/36.png)
{{% notice warning %}}
You **must empty the bucket first** before you can delete it.
{{% /notice %}}
---

### 🧹 6.3 Check remaining resources

| Service                | What to do                              |
|------------------------|-----------------------------------------|
| **S3**                 | Ensure no extra buckets remain          |
| **CloudFront**         | All distributions are deleted           |
| **ACM (SSL certificate)** | If you used a custom domain → can delete manually |
| **IAM Role / OAC**     | No need to delete if not created manually |
| **Route 53 (if any)**  | If you attached a domain → check domain zone |

---

### ✅ Done

Congratulations! You have completed the workshop on deploying a static website with **Amazon S3 and CloudFront**!

You have learned how to:
- Build a React project
- Upload content to S3
- Configure CDN and HTTPS with CloudFront
- Check, troubleshoot, and clean up AWS resources

---

👉 Next steps you can explore:
- Automate deployment with GitHub Actions
- Attach a custom domain with Route 53
- Integrate backend APIs with Lambda or Amplify