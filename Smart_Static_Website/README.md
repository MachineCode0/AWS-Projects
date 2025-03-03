# Hosting a Smart Static Website on AWS
This projects will be divided into three main parts:
1. The problem it address.
2. How to actually build it.
3. The business impact.

## 1. The Problem It Addresses
As part of my project, I aimed to host a static website for Phelyx Communication that is:
* **Globally Accessible:**
Ensuring fast load times for users worldwide.
* **Secure:**
 Protecting the website from common web exploits and ensuring data is transmitted securely.
* **Cost-Effective:**
 Keeping hosting costs low while maintaining high availability and scalability.

This project addresses these challenges by leveraging AWS services like S3, CloudFront, ACM, WAF, and CloudWatch to create a robust, secure, and scalable hosting solution tailored to your needs.
<img width="810" alt="Image" src="https://github.com/user-attachments/assets/7aeac875-e9ad-4ecf-bf19-1903ecb993da" />

## 2. How to Actually Build it
Here’s a step-by-step breakdown of how you built the solution:

**Step 1: Host the Website on S3**
* I Created an S3 bucket named www.phelyxcommunication.com and enabled Static Website Hosting.

* I Uploaded the  website files, including index.html, styles.css, and error.html.

* Made the bucket publicly accessible using a bucket policy to allow read access.

**Step 2: Accelerate Delivery with CloudFront**
* Created a CloudFront distribution with the S3 bucket as the origin.

* Configured HTTPS using an SSL/TLS certificate from AWS Certificate Manager (ACM) for the domain www.example.com.

* Set the Default Root Object to index.html to ensure the homepage loads correctly.

**Step 3: Secure the Website with WAF**
* Created a Web Application Firewall (WAF) web ACL to protect the website from common threats like SQL injection and cross-site scripting (XSS).

* Added rules to block malicious traffic and associated the web ACL with the CloudFront distribution.

**Step 4: Monitor with CloudWatch**
* Enabled CloudFront logging to an S3 bucket to store access logs.

* Created CloudWatch metrics to monitor key performance indicators like request counts, error rates, and latency.

* Set up CloudWatch alarms to notify me if error rates or latency exceed predefined thresholds.

**Step 5: Use Route 53 for DNS**
* Created a hosted zone for your domain in Route 53.

* Added an A record for www.example.com pointing to the CloudFront distribution, ensuring users can access the website using your custom domain.
