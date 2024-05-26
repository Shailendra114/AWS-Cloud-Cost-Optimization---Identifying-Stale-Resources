# AWS-Cloud-Cost-Optimization--Identifying-Stale-Resources
In this project, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

## **Description**
  The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.
# AWS CloudFront Service (AWS CDN service ) :-
AWS CloudFront is a content delivery network (CDN) service provided by Amazon Web Services (AWS). It accelerates the delivery of your website, APIs, video content, or other web assets by caching them at edge locations around the world. This ensures that users can access your content with low latency and high transfer speeds, regardless of their geographic location. CloudFront is part of AWS's suite of cloud computing services, specifically falling under the category of networking and content delivery.


**Problems Sovled by it**


AWS CloudFront solves several problems related to content delivery and web performance:

**Latency Reduction**: By caching content at edge locations closer to end-users, CloudFront reduces the time it takes for users to access your content. This helps in delivering a faster and more responsive web experience.

**Scalability**: CloudFront automatically scales to handle varying levels of traffic and demand. It can accommodate sudden spikes in traffic without impacting the performance or availability of your website or application.

**Global Reach**: With a network of edge locations spread across the globe, CloudFront enables content to be delivered to users worldwide with minimal latency. This is particularly beneficial for serving international audiences and expanding the reach of your content.

**Security**: CloudFront integrates with other AWS services to provide security features such as DDoS protection, encryption, access control, and origin authentication. This helps in securing your content and protecting it from various online threats.

**Cost-Effectiveness**: By offloading the delivery of content to edge locations, CloudFront reduces the load on origin servers and helps in minimizing bandwidth costs. Additionally, its pay-as-you-go pricing model ensures that you only pay for the resources you use, making it cost-effective for both small and large-scale applications.

Overall, AWS CloudFront improves the performance, scalability, availability, and security of web applications and content delivery, making it an essential tool for modern web development and content distribution strategies.

**How a CDN Works:**

When a user visits a website, data from that website’s server has to travel across the internet to reach the user’s computer. If the user is located far from that server, it can take a long time to load large files, such as videos or website images.
CDNs address this issue by storing website content on servers geographically closer to the users. These CDN servers act as intermediaries between the client (user’s computer) and the website server.

**Here’s how it works:
Caching**: CDNs cache (store) copies of website content (such as images, videos, scripts) on their servers. When a user requests a specific resource, the CDN delivers it from the nearest server instead of fetching it from the original website server.

**Dynamic Acceleration:**
CDNs optimize content delivery by dynamically adjusting the route and using faster connections. They choose the best server based on proximity, network conditions, and server load.

**Edge Logic Computations:**
CDNs can execute logic at the edge (near the user) to customize responses. For example, they can compress images, minify scripts, or even serve personalized content.

By distributing content across multiple locations, CDNs reduce latency, improve load times, and enhance the user experience.

**Why CDNs Are Important:**

   **Reducing Latency:** CDNs minimize the delay caused by the internet’s global and complex nature. They bring content closer to users, reducing the time it takes to load webpages.

**Efficiency:** CDNs decrease web traffic to the origin server, reducing bandwidth consumption and hosting costs for website owners.
Content Availability: CDNs handle high web traffic and prevent website crashes. Even if some CDN servers go offline, others take over to ensure uninterrupted service.

**Security:** CDNs can mitigate Distributed Denial-of-Service (DDoS) attacks by absorbing fake traffic before it reaches the origin server1.

## Interview questions based on it :-
 
**What is AWS CloudFront, and what purpose does it serve?**

**Answer:** AWS CloudFront is a content delivery network (CDN) service provided by Amazon Web Services (AWS). Its main purpose is to deliver content, such as web pages, videos, applications, and APIs, to users with low latency and high transfer speeds by caching content at edge locations close to end-users.


**How does CloudFront work? Describe its architecture.**

**Answer:** CloudFront works by caching copies of your content at multiple edge locations worldwide. When a user requests content, CloudFront routes the request to the nearest edge location that can serve the content, reducing latency and improving performance. If the content is not already cached at that edge location, CloudFront retrieves it from the origin server (such as an S3 bucket or an EC2 instance) and caches it for future requests.


**What are the benefits of using AWS CloudFront?**

**Answer:** The benefits of using AWS CloudFront include improved website performance, reduced latency, global content delivery, scalability to handle high traffic volumes, DDoS protection, SSL/TLS encryption, and cost-effectiveness by offloading traffic from origin servers.


**Explain the concept of edge locations in CloudFront. How do they contribute to performance improvement?**

**Answer:** Edge locations are AWS data centers located in various geographic locations worldwide. They serve as caching endpoints for CloudFront, allowing content to be cached closer to end-users. This proximity reduces the latency of content delivery, resulting in faster load times and improved performance for users accessing the content.


**What is the difference between origin servers and edge locations in CloudFront?**

**Answer:** Origin servers are the source of the original content, such as an S3 bucket, an EC2 instance, or an Elastic Load Balancer (ELB). Edge locations, on the other hand, are the caching endpoints of CloudFront spread across the globe. Edge locations cache content from origin servers and serve it to end-users, reducing latency and improving performance.


**How does CloudFront cache content, and what caching options are available?**

**Answer:** CloudFront caches content based on the cache control headers set by the origin server or the caching behavior specified in the CloudFront distribution settings. It offers various caching options, including time-based caching, query string parameters caching, and custom caching rules based on path patterns.


**What are the different distribution types supported by CloudFront?**

**Answer:** CloudFront supports two types of distributions: web distributions and RTMP (Real-Time Messaging Protocol) distributions. Web distributions are used for caching HTTP and HTTPS content, including web pages, images, and videos. RTMP distributions are used for streaming media files using Adobe Flash Media Server's RTMP protocol.


**Explain the process of setting up a CloudFront distribution.**

**Answer:** Setting up a CloudFront distribution involves the following steps:
Create a distribution in the AWS Management Console or using the AWS CLI/API.
Specify the origin server from which CloudFront retrieves content.
Configure caching behavior, including cache control settings and cache behaviors.
Optionally, configure security settings, such as SSL/TLS certificates, signed URLs, and access control.
Review and confirm distribution settings.
Wait for the distribution to deploy, after which CloudFront generates a domain name that you can use to access your content.

**What is the difference between a web distribution and an RTMP distribution in CloudFront?**

**Answer:** A web distribution is used for caching HTTP and HTTPS content, such as web pages, images, and videos. An RTMP distribution, on the other hand, is used for streaming media files using the Real-Time Messaging Protocol (RTMP), typically for live and on-demand video streaming.

**How does CloudFront handle dynamic content?**

**Answer:** CloudFront can cache dynamic content by forwarding requests to the origin server for each request or by using cache control headers to determine caching behavior. It supports dynamic content caching for frequently accessed content with low volatility.

**What are the security features available in CloudFront?**

**Answer:** CloudFront provides several security features, including:
HTTPS support for secure communication between CloudFront and end-users.
SSL/TLS certificate management for custom SSL certificates.
Origin access identity (OAI) to restrict access to content in the origin server.
Signed URLs and signed cookies for controlling access to private content.
Field-level encryption for protecting sensitive data in transit.
AWS Web Application Firewall (WAF) integration for protecting against common web exploits.


**Explain the process of invalidating objects in CloudFront cache.**

**Answer:** Invalidating objects in CloudFront cache allows you to remove outdated or incorrect content from edge locations before it expires. You can invalidate objects using the AWS Management Console, AWS CLI, or AWS SDKs by specifying the path or paths of the objects to invalidate. CloudFront then forwards the invalidation request to all edge locations, ensuring that subsequent requests for the invalidated objects fetch the latest content from the origin server.


**What is the role of signed URLs and signed cookies in CloudFront?**

**Answer** Signed URLs and signed cookies are security mechanisms used to control access to private content served by CloudFront. Signed URLs contain a signature that authenticates the user and grants access to specific resources for a limited time. Signed cookies work similarly but store the authentication information in an HTTP cookie. These mechanisms are commonly used to deliver secure, time-limited access to content without exposing sensitive information in the URL.


**How does CloudFront integrate with other AWS services like S3, EC2, and Lambda?**

**Answer** CloudFront integrates seamlessly with various AWS services:
With Amazon S3, CloudFront can serve static content directly from S3 buckets, improving performance and reducing latency.
With Amazon EC2, CloudFront can cache dynamic content generated by EC2 instances, enhancing scalability and reducing load on origin servers.
With AWS Lambda@Edge, CloudFront can execute serverless functions at edge locations to customize content delivery, such as modifying HTTP headers or generating dynamic responses.

**What metrics and monitoring options are available for CloudFront distributions?**

**Answer:** CloudFront provides several metrics and monitoring options, including:
Request and error rates
Data transfer and bandwidth usage
Cache hit and miss ratios
Viewer location and latency
Real-time and historical performance insights
Integration with AWS CloudWatch for customizable monitoring and alerting.


**How can you optimize CloudFront performance for global audiences?**

**Answer** To optimize CloudFront performance for global audiences, you can:
Configure multiple edge locations to cache content closer to end-users.
Use regional edge caches to serve content from nearby regions for improved latency.
Implement caching strategies based on content type and access patterns.
Enable compression and minification to reduce file sizes and improve load times.
Utilize CloudFront's content delivery optimizations, such as HTTP/2 and HTTP/3 support.







