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

**What are the pricing considerations for using AWS CloudFront?**

**Answer:** AWS CloudFront pricing is based on several factors, including data transfer out to end-users, requests (HTTP/HTTPS and invalidation requests), data transfer between AWS services (e.g., S3, EC2, and Lambda), and optional features such as field-level encryption and real-time logs. Additionally, pricing may vary based on the geographic regions served and the volume of traffic. It's essential to consider these factors when estimating costs and optimizing content delivery strategies.


**Describe a scenario where you would recommend using AWS CloudFront in an architecture.**

**Answer:** AWS CloudFront is recommended in scenarios where:
The application serves global audiences and requires low-latency content delivery.
The application experiences high traffic volumes and requires scalability.
The application serves static and dynamic content that can benefit from caching.
Security features such as HTTPS support, signed URLs, and WAF integration are required.
Cost-effectiveness and pay-as-you-go pricing models are preferred.


**What are the common challenges or limitations when using CloudFront, and how can they be addressed?**

**Answer:** Some common challenges or limitations when using CloudFront include:
Cache Invalidation: Invalidating cached content can be time-consuming and incur additional costs. Strategies such as versioned URLs or cache control headers can mitigate this challenge.
Cold Start Latency: Occasionally, CloudFront may experience higher latency during cache warm-up periods or when fetching content from the origin server. Architectural optimizations such as pre-warming caches or using regional edge caches can help mitigate cold start latency.
Pricing Considerations: CloudFront pricing can vary based on usage patterns, geographic regions, and optional features. Cost optimization strategies such as caching frequently accessed content and optimizing cache hit ratios can help manage costs effectively.


**Can you explain how CloudFront handles HTTP/2 and HTTP/3 protocols?**

**Answer:** CloudFront supports both the HTTP/2 and HTTP/3 protocols for improved performance and security. HTTP/2 enables multiplexing, header compression, and server push, reducing latency and improving page load times. HTTP/3, based on the QUIC protocol, further enhances performance by addressing the limitations of TCP-based connections, such as head-of-line blocking and connection setup overhead. CloudFront automatically negotiates the appropriate protocol based on client support and optimizes content delivery accordingly.

# AWS ECR Service (AWS Containerazation service ) :-

AWS ECR (Amazon Elastic Container Registry) is a fully managed container registry service provided by Amazon Web Services (AWS). It allows developers to store, manage, and deploy Docker container images. 

Here's an overview of its key features and functionalities:

**Private Container Registry:** AWS ECR provides a secure and private registry for storing Docker container images. Users can push, pull, and manage container images within their AWS accounts, ensuring confidentiality and control over their image repositories.

**Integration with AWS Services:** ECR seamlessly integrates with other AWS services such as Amazon ECS (Elastic Container Service), Amazon EKS (Elastic Kubernetes Service), AWS Fargate, AWS CodeBuild, and AWS CodePipeline. This integration enables developers to easily deploy containerized applications across AWS infrastructure.

**Scalable and Highly Available:** ECR is designed to be highly available and scalable, ensuring reliable access to container images for deployment. It automatically scales to accommodate increased image storage requirements and provides redundant infrastructure to minimize downtime.

**Security and Compliance:** ECR offers robust security features, including encryption at rest and in transit, IAM (Identity and Access Management) integration for fine-grained access control, and support for VPC (Virtual Private Cloud) endpoints to ensure secure communication within the AWS network. It also integrates with AWS Key Management Service (KMS) for encryption key management.

**Lifecycle Policies:** ECR supports lifecycle policies, allowing users to define rules for managing container images automatically. These policies can help optimize storage costs by automatically expiring or deleting old or unused images based on specified criteria.

**Docker CLI Compatibility:** ECR is compatible with the Docker CLI, making it easy for developers familiar with Docker to push and pull images to and from the registry using familiar commands. It also supports Docker registry API endpoints, enabling integration with third-party tools and services.

Overall, AWS ECR simplifies the process of managing container images, providing developers with a secure, scalable, and reliable solution for storing and deploying Docker container images in the AWS cloud environment.


### What is Container here ?

Imagine you're developing an application, let's say a website, and you want to deploy it to a server so that users can access it over the internet. Traditionally, you might install all the necessary software components (such as the web server, database server, and application code) directly onto the server's operating system.

However, managing software dependencies and configurations on a server can be complex and prone to errors. Additionally, it can be challenging to ensure consistency across different environments, such as development, testing, and production.

**This is where containers come in. A container is a lightweight, standalone, and executable software package that contains everything needed to run an application, including the code, runtime, system tools, libraries, and settings. Containers isolate applications from each other and from the underlying host system, ensuring that they run consistently across different environments.
Think of containers as virtualized environments for running applications. They provide a consistent and predictable runtime environment, regardless of the underlying infrastructure or operating system.**

Now, let's talk about the problem that AWS ECR solves. When you're using containers to deploy applications, you need a way to store and manage the container images. Container images are like snapshots of your application's filesystem at a specific point in time. They contain all the necessary files and configurations to run your application within a container.

AWS ECR solves the problem of managing container images by providing a secure and scalable registry service. Instead of managing container images on your own infrastructure, you can use ECR to store, manage, and deploy container images within your AWS account.

**Here's how AWS ECR helps:**

**Centralized Image Repository:** ECR provides a centralized location to store all your container images, making it easy to organize and manage your application artifacts.

**Security and Access Control:** ECR offers robust security features, such as encryption at rest and in transit, IAM integration, and VPC endpoint support, ensuring that your container images are secure and accessible only to authorized users.

**Scalability and Reliability:** ECR is a fully managed service that automatically scales to accommodate your image storage requirements and provides redundant infrastructure to ensure high availability and reliability.

**Integration with AWS Services:** ECR seamlessly integrates with other AWS services, such as ECS, EKS, Fargate, CodeBuild, and CodePipeline, enabling you to build, deploy, and manage containerized applications more efficiently.

Overall, AWS ECR simplifies the process of managing container images, providing developers with a secure, scalable, and reliable solution for storing and deploying containerized applications in the AWS cloud environment.


### What is Image here ?

Imagine you're creating a document for a school project. The document contains text, images, and formatting, and it's stored on your computer's hard drive. Now, think of this document as your application, and the computer's hard drive as the server where your application will run.

**An "image" in the context of containers is like a snapshot or a template of your application. It's a file that contains all the necessary ingredients for your application to work, just like your document contains text, images, and formatting.**

**Here's a simple breakdown of what an image contains:**

**Code and Dependencies:** Just like your document contains text and images, an image contains the code and files needed to run your application. This could be your website's HTML, CSS, JavaScript files, or any other code your application uses.

**Runtime Environment:** Your application needs a specific environment to run properly. An image includes everything needed to create that environment, such as the version of the programming language (like Python or Node.js) your application uses, libraries, and other tools.

**Configuration Settings:** Your application might have specific settings or configurations, like database connection strings or environment variables. These settings are also included in the image.

So, to sum it up, an image is like a package that contains everything your application needs to run: code, dependencies, and configuration settings. And just like you can create multiple copies of your document, you can create multiple copies of your image to run your application in different places, like on your computer for testing or on a server for the world to access over the internet.

AWS ECR (Amazon Elastic Container Registry) helps you store and manage these images, making it easier to deploy and run your applications in a consistent and reliable way. It's like having a safe and organized place to store all your document templates so you can access them whenever you need to create a new document.
















