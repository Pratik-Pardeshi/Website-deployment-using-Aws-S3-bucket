# Personal Website Deployment on Amazon S3

This guide provides detailed steps to deploy a static website (HTML) on Amazon S3. 

## Prerequisites

- An AWS account
- AWS CLI installed and configured (optional for automation)
- Static website files (HTML)

## Steps to Deploy Your Website

### 1. Create an S3 Bucket

1. **Log in to AWS Management Console**:
   - Open the AWS Management Console.
   - Navigate to the S3 service.

2. **Create a new bucket**:
   - Click on "Create bucket."
   - Enter a unique bucket name (e.g., `my-personal-website`).
   - Choose a region.
   - Keep the default settings and click "Create bucket."

### 2. Configure the Bucket for Static Website Hosting

1. **Open the S3 bucket**:
   - Select the bucket you just created.
   - Go to the "Properties" tab.

2. **Enable Static Website Hosting**:
   - Click on "Static website hosting."
   - Choose "Use this bucket to host a website."
   - Enter the index document (e.g., `index.html`).
   - Enter the error document (e.g., `error.html`), if applicable.
   - Click "Save."

### 3. Set Bucket Policy to Make the Content Public

1. **Go to the Permissions tab**:
   - Select the bucket.
   - Click on "Permissions."
   
2. **Edit the Bucket Policy**:
   - Click on "Bucket Policy."
   - Add the following policy (replace `my-personal-website` with your bucket name):

   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Sid": "PublicReadGetObject",
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::my-personal-website/*"
           }
       ]
   }
4. Upload Your Website Files
   
   Upload files:
   - Click on the "Objects" tab.
   - Click "Upload."
   - Add your files (HTML).
   - Click "Upload."

6. Access Your Website
Website URL:
Your website can be accessed using the S3 endpoint URL
AWS Management Console:
- Go to the S3 service in the AWS Management Console.
- Select your bucket.
- Go to the "Properties" tab.
- Under "Static website hosting," you will see the "Endpoint" field which shows the URL of your website.

7. Access Your Website On Web
   - Paste endpoint url to a new tab and access website
  
