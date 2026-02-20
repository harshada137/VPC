## What is a Subnet?

A **subnet** (subnetwork) is a smaller network created inside your **VPC (Virtual Private Cloud)**. It represents a specific range of IP addresses where you can launch AWS resources such as EC2 instances.

---

## Types of Subnets

### 1️⃣ Public Subnet

* Connected to the internet through an **Internet Gateway (IGW)**.
* Used for resources that need public access, such as web servers.

### 2️⃣ Private Subnet

* Does not have direct internet access.
* Used for internal resources like databases, backend services, or application servers.
* Can access the internet for outbound traffic using a **NAT Gateway** placed in a public subnet.

---

## Important Terms

| Term                       | Description                                                                                  |
| -------------------------- | -------------------------------------------------------------------------------------------- |
| **CIDR Block**             | Defines the IP address range of the subnet (e.g., `10.0.1.0/24`).                            |
| **Route Table**            | Determines how traffic from the subnet is routed (internet, other subnets, etc.).            |
| **Availability Zone (AZ)** | Each subnet belongs to only one AZ. For high availability, create subnets in multiple AZs.   |
| **NAT Gateway**            | Enables private subnet resources to access the internet securely for outbound communication. |

---

## Why Use Subnets?

1. **Security** – Separate public and private resources for better isolation.
2. **Traffic Control** – Manage routing using route tables and security groups.
3. **High Availability** – Deploy resources across multiple Availability Zones for redundancy.
