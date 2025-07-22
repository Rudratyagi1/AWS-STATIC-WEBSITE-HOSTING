# AWS S3 Static Website Hosting with ACL & Bucket Policy

![AWS S3](https://img.shields.io/badge/AWS-S3-orange?logo=amazon-aws&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-blue)
![License](https://img.shields.io/badge/License-MIT-blue)


---

## 📌 **Project Overview**
This project demonstrates **static website hosting on Amazon S3** with **object-level ACLs and bucket policies** for enhanced access control and protection of critical files like `index.html`.

Key Highlights:
- **Hosted website** on an S3 bucket.
- **Enabled ACLs** to allow **public read access**.
- **Applied bucket policy** to **deny deletion of index.html**.
- **Learned troubleshooting for public access errors**.

---

## 🎯 **Why These AWS Services?**
### **Amazon S3**
- **Why S3?**  
  - Highly durable, globally distributed storage (11 nines durability).
  - Eliminates server management vs. alternatives like Apache/Nginx.
- **Why not Azure Blob or Google Cloud Storage?**  
  - S3 has **best integration with AWS ecosystem** (IAM, CloudFront, Route53).
  - **Cheaper and simpler** static hosting vs. competitors.

### **ACL (Access Control List)**
- **Why ACL?**  
  - Allows **object-level public access**, essential for static websites.
- **Why not IAM alone?**  
  - IAM policies control AWS users/roles, not direct public access to objects.

### **Bucket Policy**
- **Why Bucket Policy?**  
  - Prevents unauthorized deletion of critical files.
- **Why not ACL alone?**  
  - ACL cannot define **explicit deny rules**.

---

## 🔧 **Tech Stack**
| Service/Tool          | Purpose                                         |
|-----------------------|-------------------------------------------------|
| **Amazon S3**         | Host static website content                     |
| **Bucket ACL**        | Allow public read for website files             |
| **Bucket Policy**     | Protect critical objects like `index.html`      |
| **AWS Console Skills**| Configuration, troubleshooting, and debugging   |

---

## 🏗 **Architecture**
![Architecture](architecture/architecture.png)

**[View Eraser.io Code](architecture/architecture.eraser)**  

---

## 📝 **Bucket Policy**
`policies/s3policy.txt`
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



 ## 📸 Screenshots

### S3 Bucket Creation
![Create Bucket](screenshots/create-bucket.png)

### Upload Website Files
![Upload Files](screenshots/upload-files.png)

### Enable Static Website Hosting
![Enable Hosting](screenshots/enable-hosting.png)

### Hosted Webpage
![Webpage](screenshots/webpage.png)


🚀 Steps to Reproduce
Create S3 bucket (ACL: Bucket Owner Preferred).

Disable Block Public Access.

Upload website files (website/index.html + assets).

Enable Static Website Hosting in S3 bucket properties.

Apply public-read ACL on objects.

Attach bucket policy to deny deletion of index.html.

🎓 Key Learning Outcomes
Understanding difference between ACL and bucket policies.

Troubleshooting S3 public access issues.

Practical implementation of secure static website hosting.




# **Next Step**
Would you like me to:  
**(a)** Add a **"Demo" section** in the README with a placeholder **S3 website URL (http://bucket-name.s3-website-region.amazonaws.com)**,  
**(b)** Create a **LinkedIn post draft** announcing this project with **high-engagement text + hashtags**?
