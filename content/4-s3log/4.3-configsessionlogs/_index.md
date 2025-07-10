---
title : "Confirm configuration & check CloudFront operation"
date: 2025-05-25 
weight : 3 
chapter : false
pre : " <b> 4.3 </b> "
---

### 4.3 Confirm configuration & check CloudFront operation
---

#### 🔹 Step 5: Review and create
At this step, you can review the information you entered earlier
- After reviewing, click **Create distribution**
- Once completed, AWS will automatically redirect you to the CloudFront information page with the status Deploying.
![Cloud](/images/anh/4.createdistribution.png)
> **Note:** Please wait for this status for a few minutes - depending on the number of edge locations you selected for deployment.

---

#### 🔹 Step 6: Check CloudFront
- In the **CloudFront** interface, select **Id**
![Cloud](/images/anh/26.png)
- In the **Distribution domain name** section
  - Make sure **CloudFront** has finished deploying by checking the **Last modified** section.
  - Click the *square icon* to copy the URL.
![Cloud](/images/anh/25.png)
- Open another tab and paste the CloudFront URL into the search bar, then press enter.
![Cloud](/images/anh/27.png)
- Congratulations, you have successfully deployed CloudFront to distribute a static website hosted on S3 without having to public the bucket or object.
