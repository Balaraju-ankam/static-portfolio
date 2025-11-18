# 🧑‍💻 Static Portfolio Website – AWS DevOps Beginner Project

This is a simple **static portfolio website** built using **HTML, CSS, and JavaScript**.  
The project is deployed using **AWS S3 Static Website Hosting**.

This project is perfect for AWS/DevOps beginners and demonstrates:
- Git & GitHub Version Control
- S3 Bucket Setup
- Static Website Hosting on AWS
- Bucket Policy & Public Access Configuration
- Deployment Steps
- Architecture Diagram

---

## 🚀 Features
- Lightweight static website
- Fully responsive
- Hosted on AWS S3
- No backend required
- Can be extended with CloudFront & CI/CD

---

## 🌐 Live Architecture Diagram

+-------------------------+
| Developer System |
| (VS Code / Terminal) |
+-----------+-------------+
|
| git push
v
+-------------------------+
| GitHub Repo |
| static-portfolio |
+-----------+-------------+
|
| Upload / Sync files
v
+-------------------------+
| AWS S3 Bucket |
| Static Website Hosting |
+-----------+-------------+
|
| Public URL
v
+--------------------------------+
| End Users (Browser Access) |
+--------------------------------+


---

## 📁 Project Structure

static-portfolio/
│
├── index.html
├── styles.css
├── script.js
└── README.md


---

## 🛠️ Tech Stack
- **Frontend:** HTML, CSS, JavaScript  
- **Cloud Platform:** AWS  
- **Services Used:** S3 Static Website Hosting  
- **Version Control:** Git & GitHub  

---

## 📦 How to Deploy to AWS S3 (Steps)

### 🔹 1. Create an S3 bucket
- Go to AWS S3 → Create Bucket
- Bucket name must be globally unique  
- Disable **Block Public Access**
- Create bucket

### 🔹 2. Enable Static Website Hosting
- Go to the bucket → Properties
- Scroll to **Static Website Hosting**
- Enable → Upload index.html
- Note the **Website Endpoint URL**

### 🔹 3. Upload Website Files
- Go to **Objects → Upload**
- Select:
  - index.html  
  - styles.css  
  - script.js  
- Upload

### 🔹 4. Add Public Read Permission
- Go to **Bucket Policy**
- Add this policy (replace YOUR-BUCKET-NAME):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
