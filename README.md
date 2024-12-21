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

### Step 4: Verify Internet Access

Once you’ve configured your bucket, it’s time to verify that your website and assets are accessible.

#### **Test the Website URL**
- Go to the **Properties** tab of your website bucket and locate the **Website Endpoint URL**.
- Copy and paste the URL into your browser to check if your website is loading correctly.


#### **5. Troubleshooting**
- **403 Forbidden Error**: Verify the bucket policy includes public read access.
- **404 Not Found Error**: Ensure that file names and paths match exactly (case-sensitive).

---

## Final Notes

🎉 **Congratulations!** You’ve successfully hosted your static website on AWS S3. Feel free to look at my blogpost on this project (https://medium.com/@somesh1st/hosting-a-website-on-amazon-s3-546332c96e7c)

Example Bucket Policy:
```json
{
    "Version": "2012-10-17",
    "Id": "Policy1734744283356",
    "Statement": [
        {
            "Sid": "Stmt1734744196822",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::static-website-p1/*"
        },
        {
            "Sid": "Stmt1734744282081",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::static-website-p1/assets/img/*"
        }
    ]
}



