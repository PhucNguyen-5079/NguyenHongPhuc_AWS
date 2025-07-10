---
title : "Preparation (React project) and build"
date: 2025-05-25 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}
Before starting this workshop, you need to prepare a static website built from popular frameworks like **React**, **Vue**, **Hugo**, or **Jekyll**. In this section, we will focus on React.
{{% /notice %}}

In this lab, you will deploy a static website to AWS using two main services:
- **Amazon S3** to store and serve website content
- **Amazon CloudFront** to distribute content globally with high performance and free HTTPS support

---

To get started, follow these steps:

### 2.1 Prepare the development environment
- Install Node.js and npm
- Install `create-react-app` to initialize a React project
- Create a folder and check the web interface on localhost

### 2.2 Build the React project for deployment
- Customize your web content in `src/`
- Run `npm run build` to create the `build/` folder with content ready to deploy

---

If you are new to React or don't know how to create a project, you can refer to the following documentation:
- [Official React Guide](https://reactjs.org/docs/getting-started.html)
{{% notice note %}}
 After completing this step, you will have a `build/` folder—this is the content to upload to Amazon S3.
{{% /notice %}}
---

### Preparation Table of Contents:
  - [2.1 Prepare the development environment](2.1-setup/)
  - [2.2 Build React project](2.2-build/)
