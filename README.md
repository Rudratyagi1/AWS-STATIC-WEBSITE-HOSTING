# AWS S3 Static Website Hosting with ACL & Bucket Policy

![AWS S3](https://img.shields.io/badge/AWS-S3-orange?logo=amazon-aws&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)

---

## 📌 **Project Overview**
This project demonstrates **hosting a static website on Amazon S3**, configuring **object-level ACLs** and **bucket policies** to secure critical files like `index.html`.  

Key Actions:
1. Create an S3 bucket with **Bucket Owner Preferred ACL**.
2. Disable **Block Public Access** to allow public hosting.
3. Upload static website files (HTML + assets).
4. Configure **object ACLs** to make files public.
5. Apply a **bucket policy** that **denies deletion of index.html** by any user.

---

## 🎯 **Why These AWS Services?**

### **Amazon S3 (Static Website Hosting)**
- **Why S3?**  
  S3 is **highly durable, scalable, and cost-effective** for hosting static websites. Unlike traditional web servers (e.g., Apache or Nginx), S3 removes the need for server management.  
- **Why not competitors (e.g., Google Cloud Storage, Azure Blob)?**  
  S3 has better **global reach**, **simpler static hosting**, and **tighter integration** with AWS IAM, CloudFront, and Route53. It’s also the **most widely adopted in enterprise setups**.

### **ACL (Access Control List)**
- **Why ACL?**  
  ACLs allow **object-level public read access** — required for a static website where files must be accessible publicly.  
- **Why not IAM roles only?**  
  IAM roles control account-level access but cannot directly make an object public. ACL is required for **fine-grained object permissions**.

### **Bucket Policy**
- **Why Bucket Policy?**  
  The policy ensures **index.html cannot be deleted** — adding a **security layer**.  
- **Why not ACL alone?**  
  ACL controls access, but **bucket policy provides explicit deny rules** and is more secure and auditable.

---

## 🔧 **Tech Stack**
| Service/Tool          | Purpose                                        |
|-----------------------|------------------------------------------------|
| **Amazon S3**         | Host static website content                    |
| **Bucket ACL**        | Public read access for website files            |
| **Bucket Policy**     | Security (prevent delete of index.html)         |
| **AWS Console Skills**| Hands-on configuration and debugging            |

---

## 🏗 **Architecture**
![Architecture][def]

**Eraser.io Diagram Code:** [architecture.eraser](diagrams/architecture.eraser)  

---

## 📝 **Bucket Policy Example**
`policies/bucket-policy.json`
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyDeleteIndexHTML",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:DeleteObject",
      "Resource": "arn:aws:s3:::<your-bucket-name>/index.html"
    }
  ]
}
🚀 Steps to Reproduce
Create an S3 bucket (ACL: Bucket Owner Preferred).

Disable Block Public Access.

Upload website files to the bucket.

Enable Static Website Hosting under Properties.

Set object ACL to public read for index.html.

Attach bucket policy to protect index.html.

🎓 What I Learned
Difference between ACL vs Bucket Policy.

How S3 static hosting works and troubleshooting access errors.

Practical security measures in AWS.

📢 Author
Rudra – AWS ML Engineer | Cloud Enthusiast
LinkedIn | GitHub

yaml
Copy
Edit

---

# **Why This Project Makes You Stand Out**
- **S3 Static Website Hosting** is a **classic real-world AWS scenario**—shows practical understanding of **IAM, ACLs, and security**.
- Demonstrates **problem-solving** (you fixed the "access error" via ACLs and policies).
- Shows **AWS Console hands-on skills** (not just theory).

---

## **Next Step**
Would you like me to **generate a ready-to-upload ZIP repo** (with `README.md`, `bucket-policy.json`, `website/index.html`, and `architecture.eraser`) so you can push it directly to GitHub?









[def]: diagrams/architecture.png