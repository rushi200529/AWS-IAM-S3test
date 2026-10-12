Rushikesh Suresh Surve 
MCA batch(jun 2026)
practical task completed 


# AWS IAM and S3 Practical Test

## Test Overview
This project demonstrates the implementation of AWS IAM and Amazon S3 services, focusing on user access management, security, storage, and permissions.

## Technologies Used
- AWS Identity and Access Management (IAM)
- Amazon Simple Storage Service (S3)
- Amazon EC2

## Test Tasks

### 1. IAM Users and Groups
Created IAM users and groups and configured group membership.

### 2. IAM Policies
Attached AWS-managed policies to control access to S3 resources.

### 3. Custom IAM Policy
Created a custom policy to allow listing the S3 bucket and reading objects.

### 4. IAM Role for EC2
Created an IAM role for EC2 with permissions to read S3 objects.

### 5. IAM Permissions Verification
Tested allowed and denied S3 operations.

### 6. S3 Bucket Creation
Created a secure S3 bucket, enabled encryption, and uploaded sample files.

### 7. Object Versioning
Organized objects using prefixes and configured bucket versioning.

### 8. S3 Bucket Policy
Configured bucket access for the developer user while keeping public access blocked.

### 9. Lifecycle Rule
Configured a lifecycle rule to transition eligible backup objects to S3 Standard-IA after 30 days.

### 10. Server Access Logging
Configured a separate destination bucket for S3 server access logs.

### 11. Encryption and Access Control
Reviewed server-side encryption, IAM permissions, bucket policies, and public access protection.

## Security Practices
- Least-privilege access
- Block Public Access
- Server-side encryption
- IAM users, groups, and roles

## Question
1)  Write one or two sentences explaining the difference between these policies?
(AmazonS3ReadOnlyAccess:- allow users to view and download S3 objects but not upload or delete them)
(AmazonS3FullAccess:- allow users to perform all S3 action including uploading,downloading,deleting objects)

2) If the bucket policy and IAM policy both 
apply, explain how you checked the effective permissions?
I checked the effective permissions by signing in as developer-user and testing access to the S3 bucket. I verified which actions were allowed or denied and confirmed that public access remained blocked.

3) Explain why a newly uploaded object may not transition immediately and mention relevant storage-duration or 
object-size considerations?
A newly uploaded object may not transition immediately because the lifecycle rule waits 30 days after object creation. S3 Standard-IA has a 30-day minimum storage duration, and objects smaller than 128 KB are generally not transitioned by default.

4) State why logs may not appear immediately after you enable logging?
   S3 server access logs do not appear immediately after enabling logging because Amazon S3 delivers them on a best-effort basis. It may take several hours for logs to arrive, and some requests might not be logged. Ensure the destination bucket and permissions are configured correctly.

5) Explain why Block Public Access is useful?
   Block Public Access helps protect an S3 bucket from unauthorized public access. It prevents accidental exposure of sensitive files to everyone on the internet, even if a bucket policy or ACL allows public access. It improves data security and privacy.
