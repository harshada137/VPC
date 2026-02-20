## Three-Tier Architecture

Three-tier architecture is a structured design pattern that separates an application into **three independent layers**: Presentation, Application, and Data.
Each layer has a specific responsibility and can scale, secure, and operate independently.

This architecture is widely used in AWS-based production environments.

---

# 1️⃣ Presentation Tier (Web Layer)

### 🎯 Purpose

* Handles client-side interaction (UI).
* Accepts and routes HTTP/HTTPS requests.
* Serves static content.

### 🛠 Technologies

* **Nginx** – Web server and reverse proxy.
* HTML, CSS, JavaScript (Frontend).

### ☁ AWS Services

* **Amazon EC2** – Hosts Nginx and frontend components.
* **Elastic Load Balancer (ELB)** – Distributes traffic across multiple web servers.
* **Amazon CloudFront** (optional) – Global CDN for faster content delivery.
* **Amazon S3** (optional) – Stores static files (images, JS, CSS).
* **AWS WAF** (optional) – Protects against web attacks (SQL injection, XSS).

### 🔐 Security

* Public subnet deployment
* Security Groups allowing only HTTP/HTTPS
* SSL/TLS via ACM (AWS Certificate Manager)

---

# 2️⃣ Application Tier (Logic Layer)

### 🎯 Purpose

* Processes business logic.
* Handles authentication, validations, and dynamic content generation.
* Connects frontend with database.

### 🛠 Technologies

* **PHP**
* **PHP-FPM** (FastCGI Process Manager)

### ☁ AWS Services

* **Amazon EC2** – Runs PHP applications.
* **Amazon ECS** – If using Docker containers.
* **Amazon Elastic Beanstalk** – Simplifies PHP deployment.
* **AWS Lambda** – For serverless logic.
* **Auto Scaling Group (ASG)** – Automatically adjusts instance count based on load.

### 🔐 Security

* Placed in a **private subnet**
* Accessible only from web tier
* IAM roles for secure AWS service access

---

# 3️⃣ Data Tier (Database Layer)

### 🎯 Purpose

* Stores structured and unstructured data.
* Handles queries and transactions.
* Maintains data integrity and consistency.

### ☁ AWS Services

* **Amazon RDS** – Managed MySQL/PostgreSQL databases.
* **Amazon Aurora** – High-performance, scalable relational database.
* **Amazon ElastiCache** – Caching layer using Redis/Memcached.
* **Amazon DynamoDB** (optional) – NoSQL database if required.

### 🔐 Security

* Located in private subnet
* No public internet access
* Access controlled by security groups
* Encrypted at rest and in transit
* Automated backups and Multi-AZ deployment

---

# 🔄 End-to-End Request Flow

1. User sends request → Load Balancer
2. Load Balancer → Web Server (Nginx)
3. Nginx → PHP-FPM (Application logic)
4. Application → Database (RDS/Aurora)
5. Response travels back → User

---

# 🚀 Key Benefits

### ✅ Scalability

Each tier scales independently (e.g., more web servers during high traffic).

### ✅ High Availability

Multi-AZ deployment ensures fault tolerance.

### ✅ Security Isolation

Each layer runs in separate subnets with controlled access.

### ✅ Maintainability

Changes in one layer do not directly impact others.

### ✅ Performance Optimization

Caching (ElastiCache), CDN (CloudFront), and load balancing improve speed.

---

# 📌 Real-World Production Setup Example

* Public Subnet → Load Balancer + Web Tier
* Private Subnet → Application Tier
* Private Subnet (Separate) → Database Tier
* NAT Gateway → Outbound internet for private instances
* Monitoring → CloudWatch
* Logging → CloudTrail
