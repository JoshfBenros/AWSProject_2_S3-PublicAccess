# AWS Project 2: S3 Public Access Lab

## Overview
This project demonstrates how to configure **Amazon S3 bucket permissions** and test **public vs. private access**.  
The goal was to understand how AWS handles access control through **Block Public Access settings** and to apply security best practices.  

This lab builds on my previous work in **IAM & Least Privilege** by focusing on **S3 bucket security**.

---

## Goals
- Create an S3 bucket and upload a test file.  
- Attempt to access the file publicly (unauthenticated).  
- Apply **Block Public Access** and test again.  
- Demonstrate AWS default security behavior and reinforce cloud security principles.  

---

## Steps Taken

### 1. S3 Bucket Creation
- Logged in as `josh-admin`.  
- Created a bucket: **`jb-s3-public-lab-project2`** in region `us-east-2`.  
- Left **Block Public Access** initially **unchecked** to allow testing.  
- Enabled **default server-side encryption (SSE-S3)**.  
- Uploaded a file: **hello.txt**.  

---

### 2. Testing Public Access
- Copied the **Object URL** for `hello.txt`.  
- Attempted to open it in a browser:  
  - **Result:** *Access Denied* (AWS default behavior, since even with Block Public Access disabled, bucket policies or object ACLs are still required for true public access).  

---

### 3. Enforcing Security
- Returned to bucket permissions.  
- Enabled **Block All Public Access**.  
- Tested the object URL again.  
  - **Result:** *Access Denied* (confirmed bucket cannot be exposed publicly).  

---

## Results
- Even when **Block Public Access** was disabled, S3 did not allow open access without explicit policies.  
- Once **Block Public Access** was turned on, all attempts to access files via a public URL were consistently denied.  
- This confirms AWS **secure-by-default posture** and shows how administrators can enforce best practices.  

---

## Reflection
- AWS intentionally prevents accidental public exposure of S3 buckets.  
- **Block Public Access** is a safeguard that should always be enabled in production environments.  
- This lab reinforced my understanding of **S3 object security**, **default encryption**, and **public vs. private access control**.  

---

## Screenshots

- **bucket-public.png** → S3 bucket created with public access initially allowed.  
- **bucket-secured.png** → Block Public Access enabled, securing the bucket.  
- **bucket-secured2.png** → Confirmation that Block Public Access is active.  
- **file-access-denied-first.png** → First attempt to access the file via public URL returned **Access Denied**.  
- **file-access-denied-end.png** → Second test confirmed continued denial of public access.  
- **file-publicly-accessible.png** → Controlled test showing what it looks like when a file is publicly viewable before being restricted.  

---

