---
title : "Configure CloudFront and HTTPS"
date: 2025-05-25 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---

## 4. Configure CloudFront and HTTPS

### 🔰 Introduction to CloudFront

**Amazon CloudFront** is a CDN (Content Delivery Network) service provided by AWS. It helps deliver web content to users worldwide with fast speed, low latency, and high reliability through AWS's network of Edge Locations.

CloudFront works by **caching static content** (HTML, CSS, JS, images, videos...) from the origin (such as Amazon S3) and distributing it through servers closest to users.

---

### 🎯 Benefits of using CloudFront

- 🚀 **Faster page loads** for users from any country
- 🔐 **Free HTTPS support** with default SSL certificate
- 📉 **Reduces load on S3** because data is cached at Edge Locations
- 🔎 **Protects your website from unusual access** via CloudFront Shield (advanced)
- 🧾 **Access logging** and easy integration with monitoring tools like CloudWatch
- 💰 **Save on bandwidth costs** if you configure the right Price Class

---

### 📦 What you will do in this section:

1. **Create a CloudFront Distribution** connected to your S3 bucket
2. Configure CloudFront to:
   - Distribute static website content
   - Automatically redirect HTTP → HTTPS
3. Check the public link for HTTPS and correct operation
4. Troubleshoot common errors (if any)

---

👉 After completing this section, your website will:
- Be accessible globally
- Run faster and more securely
- Be ready to go public for end users
