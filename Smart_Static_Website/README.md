# Hosting a Smart Static Website for Phelyx Communication on AWS
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
<img width="860" alt="Image" src="https://github.com/user-attachments/assets/39280916-d845-4528-8b24-569f2abfa96a" />

## 2. How to Actually Build it
Here’s a step-by-step breakdown of how you built the solution:

**Step 1: Host the Website on S3**
* I Created an S3 bucket named www.phelyxcommunication.com and enabled Static Website Hosting.

* I Uploaded the  website files, including index.html, styles.css, and error.html.

* Made the bucket publicly accessible using a bucket policy to allow read access.

**Step 2: Accelerate Delivery with CloudFront**
* Created a CloudFront distribution with the S3 bucket as the origin.

* Configured HTTPS using an SSL/TLS certificate from AWS Certificate Manager (ACM) for the domain www.phelyxcommunication.com

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

* Added an A record for www.phelyxcommunication.com pointing to the CloudFront distribution, ensuring users can access the website using the custom domain.

## 3. The Business Impact
The solution delivers significant business value for Phelyx Communication by:

**1. Improving User Experience:**

   * Faster load times and global availability through CloudFront’s edge locations.

   * Reliable uptime and scalability to handle traffic spikes, ensuring users can always access the website.

**2. Enhancing Security:**

   * Protection against common web exploits using WAF.

   * Secure data transmission with HTTPS via ACM, ensuring user data is protected.

**3. Reducing Costs:**

   * Pay-as-you-go pricing with AWS services ensures cost efficiency.

   * Free Tier usage for S3, CloudFront, and WAF reduces initial costs, making it an affordable solution for small to medium-sized businesses.

**4. Enabling Better Decision-Making:**

   * Real-time monitoring and alerts via CloudWatch help you identify and resolve issues quickly.

   * Logs and metrics provide insights into website performance and user behavior, enabling data-driven decisions.
## Conclusion
This project demonstrates how you successfully built a smart static website hosting solution on AWS for **Phelyx Communication**. By addressing performance, security, scalability, and cost challenges, you’ve created a reliable and secure online presence that delivers value to your business. The use of AWS services like S3, CloudFront, ACM, WAF, and CloudWatch ensures that your website is fast, secure, and cost-effective, while also providing the tools to monitor and optimize its performance over time.
