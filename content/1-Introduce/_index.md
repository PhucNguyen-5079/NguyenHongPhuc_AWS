---
title : "Introduction"
date: 2025-05-25 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
![Cloud](/images/anh/Bangdiagram.drawio.png)
**Amazon S3 and CloudFront** are two core AWS services that help you deploy a **static website** quickly, cost-effectively, and securely.  
You don't need to manage servers, install Nginx or Apache, and you can still distribute your website globally with high performance and secure HTTPS.

When using S3 to host your website and CloudFront to distribute content (CDN), you get the following benefits:

- No need to rent a dedicated server (EC2) or VPS.
- No need to install web server software like Apache or Nginx.
- No need to open ports or configure firewalls.
- Website can be accessed globally via **CloudFront CDN**, speeding up load times.
- **Free HTTPS** support via CloudFront certificates.
- Can use your own domain or the default link like `https://xxxxx.cloudfront.net`.
- S3 supports versioning, public/private access, and easy integration with other services.
- Deploying static sites like **React**, **Vue**, **Hugo**, **Jekyll**... is extremely simple with just a `build/` folder.

With these advantages, using **S3 + CloudFront** is a great choice for deploying personal websites, portfolios, landing pages, or even static blogs—without worrying about server costs or connection security.

You no longer need to deploy EC2 servers or Bastion Hosts to make your site public—the whole process is **completely serverless** and can **auto scale without limits**.
