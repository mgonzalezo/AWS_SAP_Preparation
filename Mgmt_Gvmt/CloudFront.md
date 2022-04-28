# AWS CloudFront

- CloudFront distribution is designed for optimizing content delivery and content caching.
- Field-level encryption adds an additional layer of security, along with HTTPS, that lets you protect specific data throughout system processing.
- Field-level encryption allows you to securely upload user-submitted sensitive information to your web servers
Sensitive information provided by your clients is encrypted at the edge closer to the user and remains encrypted throughout your entire application stack.
- To use it you configure your CloudFront distribution to specify the set of fields in POST requests that you want to be encrypted.
- It is better to add field-level encryption than Custom SSL to protect the credit card information.
- To increase your cache hit ratio, you can configure your origin to add a Cache-Control max-age directive to your objects
- To restrict access to content that you serve from Amazon S3 buckets:
  - Create a special CloudFront user called an origin access identity (OAI) and associate it with your distribution.
  - Configure your S3 bucket permissions so that CloudFront can use the OAI to access the files in your bucket single CloudFront web distribution.
- To serve different types of requests from multiple origins
  - Static content from an Amazon Simple Storage Service (Amazon S3) bucket and dynamic content from a load balancer
- CloudFront supports content uploads via POST, PUT, other HTTP Methods.
- There is a limited connection timeout to the origin (60 seconds).  If uploads will take several minutes, the connection might get terminated.
- If you want to optimize performance when uploading large files to Amazon S3, it is recommended to use **Amazon S3 Transfer Acceleration**
- A signed URL includes additional information, for example, expiration date and time, that gives you more control over access to your content.
- Accepts well-formed connections to prevent many common DDoS attacks like SYN floods and UDP reflection attacks
- OAI is mainly used to restrict access to objects in S3 bucket, but not provide encryption to specific fields.
- To require that users access your content through CloudFront URLs, you do the following tasks:
  - Create a special CloudFront user called an origin access identity and associate it with your CloudFront distribution.
  - Give the origin access identity permission to read the files in your bucket.
  - Remove permission for anyone else to use Amazon S3 URLs to read the files.
- AWS recommends using signed URLs.
- You can set up an origin failover by creating an origin group with two origins with one as the primary origin and the other as the second origin.
- Use your own SSL certificates with Amazon CloudFront at no additional charge with Server Name Indication (SNI) Custom SSL.
- CloudFront logs are only periodically saved to Amazon S3. In some cases, this process occurs up to 24 hours later. This solution will not be able to quickly create AWS WAF rules during an attack.

## Sample Question:

Q. How should I choose between Transfer Acceleration and Amazon CloudFront’s PUT/POST? 

- Transfer Acceleration optimizes the TCP protocol and adds additional intelligence between the client and the S3 bucket, making Transfer Acceleration a better choice if a higher throughput is desired. If you have objects that are smaller than 1GB or if the data set is less than 1GB in size, you should consider using Amazon CloudFront's PUT/POST commands for optimal performance.

Source: From <https://stackoverflow.com/questions/36882595/are-there-any-difference-between-amazon-cloudfront-and-amazon-s3-transfer-accele> 

- You cannot use CloudFront for database caching. CloudFront is primarily used to securely deliver data, videos, applications, and APIs to customers globally with low latency and high transfer speeds.

Source: From <https://portal.tutorialsdojo.com
