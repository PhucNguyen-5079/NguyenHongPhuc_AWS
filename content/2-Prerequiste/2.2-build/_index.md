---
title : "Build React project"
date: 2025-05-25 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

## Build React project

In this section, you will **use a pre-provided React project** to save time on initialization. After downloading the project, you will install dependencies, edit, test, and build it to get ready for deployment to Amazon S3.

---

### 🔹 Step 1: Download the React project

You can download a sample project from GitHub or from the provided `.zip` file:

[📦 Download React project (.zip)](../downloads/react-project.zip)

### 🔹 Step 2: Install dependencies

In the project directory, run:

```bash
npm install
```

### 🔹 Step 3: Edit website content

Open the file:

```text
src/App.js
```

→ Edit the UI, text, images, etc. as needed.
→ This is the part that will be displayed after you deploy.

### 🔹 Step 4: Test the website locally

Run:

```bash
npm start
```

→ The browser will automatically open http://localhost:3000
→ Check the interface and displayed content.

### 🔹 Step 5: Build the project for deployment

After editing, run:

```bash
npm run build
```

→ This command will create the folder:

```text
build/
```

📦 The build/ folder contains all web content ready to upload to Amazon S3.

👉 Next: Move to Step 3 – Upload content to S3

