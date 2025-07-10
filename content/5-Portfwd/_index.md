---
title : "Check website, fix CORS & 404 errors"
date: 2025-05-25 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

## 5. Check your website and troubleshoot common errors

After deploying your website to S3 and configuring CloudFront, the next step is to check if your website is working properly and handle some common issues:
{{% notice warning %}}
  Blank page
{{% /notice %}}
{{% notice warning %}}
  403 or 404 error
{{% /notice %}}
{{% notice warning %}}
  CORS error when calling APIs or loading resources
{{% /notice %}}

---

### 🔍 5.1 Access the CloudFront URL

After successfully creating the Distribution, you will have a URL like:

```
https://dxxxxxxxxxxxxxx.cloudfront.net
```

➡️ Open this link in your browser to check your website.

---

### ✅ 5.2 Check if the page displays correctly

| Status                  | Meaning                                      |
|-------------------------|----------------------------------------------|
| ✅ Displays correctly   | Website works well, no action needed         |
| ❌ Blank page or 403    | Might be missing `index.html` or wrong root  |
| ❌ 404 for images/CSS   | Might have uploaded to wrong location in S3  |

---

### 🧪 5.3 Common issues & solutions

---

#### ❗ Blank page or `403 Forbidden`

**Common causes:**
- CloudFront cannot find `index.html`
- You have not set `Default root object` in CloudFront

**How to fix:**
1. Go to CloudFront → Select your distribution
2. Tab **General** → click **Edit**
3. Enter in **Default root object**:  
index.html
4. Click Save → Wait 1–2 minutes → Refresh the website

---

#### ❗ `404 Not Found` error

**Common causes:**
- You uploaded the **entire `build/` folder** instead of just its contents
- File is missing or has the wrong path

**How to fix:**
- Go to S3 bucket → Check if files are at the root
  - Correct: `/index.html`, `/static/js/...`
  - Incorrect: `/build/index.html` ❌
- If incorrect → Delete and re-upload the correct contents of `build/`

---

#### ❗ CORS (Cross-Origin Resource Sharing) error

**Cause:**
- Browser blocks when your site calls APIs from another domain without CORS enabled

**How to fix (basic for S3):**
1. Go to S3 bucket
2. Tab **Permissions** → **CORS configuration**
3. Add the following simple configuration:

```xml
<CORSConfiguration>
  <CORSRule>
    <AllowedOrigin>*</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
    <AllowedHeader>*</AllowedHeader>
  </CORSRule>
</CORSConfiguration>
```
{{% notice warning %}}
  This is a fully open configuration (for workshop use). In production, you should restrict the domain.
{{% /notice %}}
🧪 Tips for checking your website after deployment

| What to check           | What could be wrong?                      |
|-------------------------|-------------------------------------------|
| Is the website visible? | If not → check index.html                 |
| CSS/JS links broken?    | Check the Network tab                     |
| Console errors?         | Check the Console tab                     |
| HTTPS padlock present?  | If not → check CloudFront                 |
