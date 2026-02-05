## 🚀 How to Increase the Size of an EBS Volume (AWS)

### 🔹 Prerequisites

* An **EBS volume** must be created
* The volume must be **attached to an EC2 instance**
* EC2 instance should be **running** (for online resize)

---

## 🛠️ Step-by-Step Procedure

### 1️⃣ Launch and Access EC2

* Launch an **EC2 instance**
* SSH into the instance
* Check the attached disks:

```bash
lsblk
```

> This command displays the block devices and current EBS size.

---

### 2️⃣ Modify EBS Volume Size

* Go to **AWS Console → EC2 → Volumes**
* Click on the **Volume ID**
* Select **Modify Volume**
* Increase the **Size** (EBS size can only be increased, not decreased)
* Click **Modify**

---

### 3️⃣ Verify Volume Size Change

After modification is complete, return to the EC2 instance:

```bash
lsblk
```

> You should now see the updated EBS size.

Check current filesystem usage:

```bash
df -h
```

---

### 4️⃣ Extend the Partition

Extend the partition to use the new space:

```bash
sudo growpart /dev/xvda 1
```

* `/dev/xvda` → disk name
* `1` → partition number (usually root partition)

Verify:

```bash
lsblk
```

---

### 5️⃣ Extend the Filesystem

For **XFS filesystem** (default for Amazon Linux):

```bash
sudo growfs -d /
```

* `/` → mount point of the root directory

Verify final size:

```bash
df -h
```

---

## ✅ Result

🎉 **The EBS volume size has been successfully increased and is now usable by the OS.**

---

## ⚠️ Important Notes

* 📌 **Non-root (data) volumes** can be attached or detached **while EC2 is running or stopped**
* 🔒 **Root volumes** require the EC2 instance to be **stopped** before attach/detach
* 📈 EBS volume size **can only be increased**, never decreased

---

### 💡 Interview Tip:

> *“EBS volume resizing is a two-step process: first increase the volume size from AWS, then extend the partition and filesystem inside the OS.”*

