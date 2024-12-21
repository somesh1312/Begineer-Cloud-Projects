# Hosting a Static Website on AWS S3

This repository provides a step-by-step guide to hosting a static website on **Amazon S3**. Follow along to learn how to efficiently deploy your static site using Amazon's cloud storage solution.

---

## Steps to Host Your Static Website

### Step 1: Create an S3 Bucket and Upload `index.html`
1. Log in to the [AWS Management Console](https://aws.amazon.com/console/).
2. Create an S3 bucket with a unique name (e.g., `my-portfolio-website`).
3. Upload your `index.html` file to the bucket.

### Step 2: Configure the S3 Bucket for Static Website Hosting
1. Navigate to the **Properties** tab of the bucket.
2. Enable **Static Website Hosting** and specify `index.html` as the **Index Document**.
3. Save the changes.

### Step 3: Provide Public Access
#### Remove Public Access Block
1. Go to the **Permissions** tab and edit the **Block Public Access** settings.
2. Uncheck **Block all public access** and confirm the changes.

#### Set Bucket Policy
1. Use the **Policy Generator** to create a bucket policy allowing public read access.
2. Apply the policy to your bucket.

Example Bucket Policy:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::your-bucket-name/*"
        }
    ]
}
# Begineer-Cloud-Projects
