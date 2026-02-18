# Jump Server (Bastion Host) in a VPC

A **Jump Server**, also known as a **Bastion Host**, is a special instance in a VPC used to **securely access private instances** that do not have direct internet connectivity.

---

## Why Use a Jump Server?

* Private instances **lack public IPs**.
* Direct SSH/RDP access from the internet is **not possible**.
* The Jump Server acts as a **secure gateway**, enabling controlled access to private resources.

---

## Typical Setup

1. **Launch Jump Server** in a **public subnet** with:

   * A **public IP address**
   * Security group rules allowing SSH (port 22) from your IP

2. Place **target instances** in a **private subnet**.

3. **Access flow:**

   * SSH into the Jump Server
   * From there, SSH into private instances

---

## Security Best Practices

* Use **key-based SSH authentication**.
* Restrict SSH access to your IP only.
* Use **IAM roles** and **session logging** if integrating with AWS Systems Manager.
* Consider **AWS SSM Session Manager** as a more secure, auditable alternative.

---

## Example Network Flow

```
[Your Laptop]
       |
       | SSH (port 22)
       v
[Jump Server - Public Subnet]
       |
       | SSH (port 22)
       v
[Private EC2 - Private Subnet]
```

