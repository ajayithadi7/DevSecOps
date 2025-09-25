

# 🖥️ Introduction to Servers & AWS EC2

## 📌 What is a Server?

A **server** is a powerful computer designed to **process, store, and manage data** for other devices or applications.
Servers can:

* Host websites
* Run applications
* Manage databases

They can operate locally (on-premises) or remotely (in the cloud).

---

## 🆚 Physical vs. Cloud Servers

| Feature         | Physical Servers                               | Cloud Servers                               |
| --------------- | ---------------------------------------------- | ------------------------------------------- |
| **Location**    | On-premises / Data centers                     | Hosted on the internet (AWS, Azure, GCP)    |
| **Maintenance** | Requires manual upkeep (power, cooling, space) | Managed by provider – no physical work      |
| **Scaling**     | Time-consuming and expensive                   | Instant and cost-effective                  |
| **Control**     | Full hardware control                          | Full OS/app control without hardware hassle |

🔹 **Physical servers**: Better for industries needing dedicated on-prem infrastructure due to regulatory or latency reasons.
🔹 **Cloud servers**: Ideal for most use cases (scalable, cost-efficient, easy to manage).

---

## ☁️ What is AWS EC2?

**Amazon EC2 (Elastic Compute Cloud)** is a web service that lets you rent **virtual servers** in the cloud.
You can:

* Run applications
* Host websites
* Process data
* Fully control OS, software, and configurations

### ⚡ Key Features of EC2:

* **Scalability** – scale up/down automatically
* **Variety of Instances** – different CPU, RAM, storage options
* **Pay-as-You-Go** – only pay for what you use
* **Security** – integrates with AWS IAM
* **Global Reach** – launch servers in multiple AWS regions

---

## 🚀 How to Launch an EC2 Instance (Step-by-Step)

1. **Login** to your AWS account.
2. **Open EC2** in the AWS Management Console.
3. Click **“Launch Instances”**.
4. **Name your instance** (e.g., `MYSERVER`).
5. **Choose an AMI** (Amazon Machine Image) – e.g., Amazon Linux 2023 (Free Tier).
6. **Select Instance Type** – e.g., `t2.micro` or `t3.micro` (Free Tier).
7. **Create/Select Key Pair** for secure login:

   * Public key stored in AWS
   * Private `.pem` file downloaded to your system
8. **Configure Network Settings**:

   * Security Groups = Virtual Firewalls
   * Inbound Rule: Allow **SSH (port 22)** to connect
   * Outbound Rule: Control outgoing traffic
9. **Configure Storage**:

   * AWS EBS (Elastic Block Store)
   * Min 8 GB (Free Tier up to 30 GB)
10. **Click “Launch Instance”**
11. **View Running Instances** under “Instances” list

---

## 🗑️ How to Terminate (Delete) an EC2 Instance

1. Select your instance.
2. Click **Instance State → Terminate**.
3. Wait ~30 seconds → state changes from “shutting down” to “terminated”.

> **Note:**
>
> * EBS volume is deleted automatically.
> * Key pairs and Security Groups remain (free to reuse).

---

## ✅ Conclusion

AWS EC2 makes it simple to deploy servers without managing physical infrastructure.
Its **flexibility**, **scalability**, and **cost-efficiency** make it perfect for developers, businesses, and anyone wanting to leverage cloud power.

---



