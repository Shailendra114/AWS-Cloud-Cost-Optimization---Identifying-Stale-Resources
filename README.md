# AWS-Cloud-Cost-Optimization--Identifying-Stale--Resources
In this project, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

# **Description**
  The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.
## AWS CloudFront Service (AWS CDN service ) :-
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

