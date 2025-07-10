---
title : "Create S3 bucket and upload website content"
date: 2025-05-25 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

## 3. Create S3 bucket and upload website content

After you have the `build/` folder from your React project (or `public/` if using Hugo), you will upload all its contents to Amazon S3 so your website can be accessed publicly.

---

### 🔹 3.1 Access Amazon S3 service

1. Go to: [https://s3.console.aws.amazon.com/s3](https://s3.console.aws.amazon.com/s3)
2. Click **Create bucket**
![Cloud](/images/anh/3-s3.png)
3. Enter the following information:
   - **Bucket name**: globally unique name, e.g., `phuccg-react-web`
   - **Object Ownership**: select ACLs disabled (recommended)
![Cloud](/images/anh/1.png)
4. In **Block Public Access**, **uncheck "Block all public access"**
5. Confirm the warning → check ✅ the confirmation box
![Cloud](/images/anh/3.s3.block.png)
6. Click **Create bucket**
![Cloud](/images/anh/3.s3create.png)

---

### 🔹 3.2 Upload web content to the bucket

1. Go to the bucket you just created
![Cloud](/images/anh/3.s3taoxong.png)
2. Click **Upload**
![Cloud](/images/anh/2.png)
3. Select all contents inside the `build/` folder
{{% notice note %}}
 **DO NOT upload the entire `build` folder**, only the files inside
{{% /notice %}}
![Cloud](/images/anh/3.png)
4. Click **Upload**
![Cloud](/images/anh/4.png)

---

### 🔹 3.3 Make files public

1. Select all uploaded files → Click **Actions > Make public**
2. Confirm when prompted
{{% notice note %}}
 Or you can use a Bucket Policy in the next step to make everything public.
{{% /notice %}}

---

### 🔹 3.4 Enable Static website hosting

1. In the bucket, go to the **Properties** tab
2. Scroll down to **Static website hosting**
3. Click **Edit**, then enable:
![Cloud](/images/anh/5.png)
   - Enable → ✅ `Enable`
   - **Index document**: `index.html`
   - **Error document**: `index.html` (or `error.html` if you have one)
   ![Cloud](/images/anh/6.png)
4. Click **Save changes**
![Cloud](/images/anh/7.png)
---

### ✅ Result

You will see a link like this:

```plaintext
http://phuccg-react-web.s3-website-ap-southeast-1.amazonaws.com
```
![Cloud](/images/anh/8.png)
---

### 🔹 3.5 Make files public using Bucket Policy

1. In the bucket, go to the **Permissions** tab
![Cloud](/images/anh/9.png)
2. Select **Bucket policy**
3. Click **Edit**, then paste this JSON:
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
👉Replace **phuccg-react-web** with your actual bucket name.

4. Click **Save changes**
![Cloud](/images/anh/12.png)
---

### 🔹 3.6 Check the website

After completing the above steps, the next step is to check your website
1. In the bucket, go to the **Objects** tab
2. Select the **phuccg-react-web** folder you uploaded
3. Select the **index.html** file
![Cloud](/images/anh/13.png)
4. Find the details for **index.html**
5. Select **Object URL**.
![Cloud](/images/anh/14.png)
6. Open the URL in a new browser tab
![Cloud](/images/anh/15.png)
