---
title : "Chuẩn bị môi trường phát triển"
date: 2025-05-25 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

## Hướng dẫn cài đặt môi trường phát triển React

### Cài đặt Node.js và npm

1. Truy cập [https://nodejs.org](https://nodejs.org) và chọn bản LTS phù hợp với hệ điều hành của bạn.
2. Cài đặt như các phần mềm thông thường trên Windows.
3. Mở terminal (Command Prompt hoặc PowerShell) và kiểm tra cài đặt:

```powershell
node -v
npm -v
```

### Cài đặt create-react-app và khởi tạo project React

1. Cài đặt `create-react-app` toàn cục:

```powershell
npm install -g create-react-app
```

2. Tạo một project React mới:

```powershell
npx create-react-app my-web
cd my-web
```
