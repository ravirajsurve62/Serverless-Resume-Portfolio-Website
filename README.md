# Serverless-Resume-Portfolio-Website
Developed and deployed a serverless portfolio website using Amazon S3 to host and publish resumes and documents. Automated document publishing and JSON index updates using AWS Lambda and S3 event triggers, with IAM-based access control and CloudWatch logging for monitoring.
# Serverless Resume Portfolio Website on AWS

A serverless web application that automatically publishes resumes, certificates, and project documents to a public portfolio website using AWS managed services.

## 🌐 Live Demo

**https://staging.d35ho2lp7ydewy.amplifyapp.com/**

## 📌 Project Overview

This project implements an automated, serverless Resume Portfolio Website using Amazon Web Services (AWS). It allows documents uploaded to a private Amazon S3 bucket to be automatically processed and published to a public website using AWS Lambda.

The website dynamically displays published documents and provides search and download functionality. AWS IAM manages access permissions, while Amazon CloudWatch records execution logs for monitoring and troubleshooting.

## 🛠️ Tools & Technologies

- **Cloud Platform:** Amazon Web Services (AWS)
- **Storage & Hosting:** Amazon S3
- **Serverless Computing:** AWS Lambda
- **Programming:** Python, Boto3
- **Access Control:** AWS IAM
- **Monitoring & Logging:** Amazon CloudWatch
- **Frontend:** HTML, CSS, JavaScript
- **Data Indexing:** JSON

## ⚙️ System Architecture

The application follows an event-driven serverless architecture.

```text
User uploads a document
          |
          v
Private Amazon S3 Bucket
          |
          v
S3 ObjectCreated Event
          |
          v
AWS Lambda Function
          |
          v
Copies document to website bucket
          |
          v
Updates resumes.json
          |
          v
Public S3-Hosted Website
          |
          v
Search and Download Documents

CloudWatch --> Lambda Execution Logs
IAM         --> Access Permissions
```

## ✨ Key Features

- **Automated Publishing:** New document uploads trigger an AWS Lambda function automatically.
- **Serverless Hosting:** Website files are hosted using Amazon S3 static website hosting.
- **Private Upload Storage:** Uploaded documents remain in a separate private bucket before processing.
- **Dynamic Document Listing:** A JSON index is updated automatically when documents are published.
- **Search Functionality:** Users can search for documents by name.
- **Download Functionality:** Visitors can access published documents through the website.
- **Access Control:** IAM roles and policies manage the permissions required by the Lambda function.
- **Monitoring:** Amazon CloudWatch captures execution logs to help verify processing and troubleshoot errors.
- **Custom Error Page:** A custom 404 page handles invalid page requests.

## 🔄 Workflow

1. A user uploads a resume or document to the private S3 bucket.
2. An S3 object-created event triggers the Lambda function.
3. The Lambda function retrieves the uploaded document using Python and Boto3.
4. The document is copied to the public website bucket.
5. The Lambda function updates `resumes.json` with the published document's name.
6. The website reads the JSON index and displays the available documents.
7. Visitors can search for and download published documents.
8. CloudWatch logs record the Lambda execution for monitoring and debugging.

## 📂 Website Files

| File | Purpose |
|---|---|
| `index.html` | Main portfolio website interface |
| `resumes.json` | JSON index of published documents |
| `error.html` | Custom 404 error page |
| `documents/` | Folder containing published documents |

## 🔐 AWS Services Configuration

- **Amazon S3:** Two buckets are used for private uploads and public website hosting.
- **AWS Lambda:** Processes S3 upload events, copies documents, and updates the JSON index.
- **AWS IAM:** Provides the Lambda function with the required S3 and CloudWatch permissions.
- **Amazon CloudWatch:** Stores execution logs for verification and troubleshooting.

## 🧪 Testing & Verification

The following functionalities were tested:

- Static website hosting and page loading.
- Automatic Lambda invocation after document uploads.
- Document copying from the private bucket to the website bucket.
- Automatic updates to `resumes.json`.
- Document listing, search, and download functionality.
- Custom 404 error page.
- Lambda execution logs in CloudWatch.

## 🎯 Learning Outcomes

- Understanding serverless application architecture.
- Deploying static websites using Amazon S3.
- Implementing event-driven automation using AWS Lambda.
- Working with Python and Boto3 for AWS service integration.
- Configuring IAM roles and permissions.
- Monitoring serverless applications using Amazon CloudWatch.
- Integrating frontend web technologies with cloud services.

## 🚀 Future Improvements

- Add HTTPS support through Amazon CloudFront.
- Introduce authenticated document uploads.
- Add document categories and filtering.
- Improve access control and document management.

## 👨‍💻 Author

**Raviraj Surve**
