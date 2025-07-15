# Network Security & Automation Portfolio

📌 *Collection of real-world network security automation projects including Palo Alto firewall automation, cloud networking, and operational scripts.*

---

Welcome! I’m **Vin**, a Network Security Engineer passionate about automating and securing enterprise infrastructure.  
This portfolio highlights my hands-on work in areas such as:

- 🔐 Palo Alto firewall automation using Ansible  
- 🔄 Backup and monitoring scripts for network devices  
- ☁️ Cloud network architecture (AWS) and DMZ design  
- ⚙️ Infrastructure as Code (IaC) using Terraform  

---

## 🔧 Projects Overview

### Ansible Playbooks
- **palo_alto_firewall.yml** — Automates NAT and security policy deployment on Palo Alto firewalls with audit logging for HIPAA compliance.
- **[palo_alto_block_non_compliant_apps.yml](https://gist.github.com/vin18-byte/7148362aba86cdd3f564fd257139ab66)** — Denies non-compliant apps (Telnet, FTP, SMB) on Palo Alto firewalls for HIPAA/PCI-DSS compliance.


### 📁 Scripts
- **`backup_firewall_configs.py`** — Automates secure backups of firewall configurations across multiple vendors.
- **`monitor_logs.sh`** — Parses and analyzes firewall logs for key security events (e.g., denied traffic, port scans).

### 📁 Documentation
- **`DMZ_design_guide.md`** — A practical guide to designing a secure and scalable DMZ architecture in AWS, including Palo Alto VM-Series integration.

# Secure DMZ Architecture in AWS with AWS WAF

This project demonstrates a secure, scalable DMZ design implemented in AWS, featuring:

- **VPC with Public and Private Subnets:** Public subnet hosts internet-facing resources (ALB, Bastion Host, Web Servers). Private subnet houses application and database servers isolated from direct internet access.
- **Internet Gateway (IGW):** Enables inbound/outbound internet connectivity for public subnet.
- **Application Load Balancer (ALB):** Distributes incoming traffic across web servers, improving availability and fault tolerance.
- **AWS WAF Integration:** Provides protection against common web exploits by filtering malicious requests before they reach the ALB.
- **Bastion Host:** Secure jump server for administrative access to private instances.
- **NAT Gateway:** Allows private instances to access the internet securely for updates and patches.
- **Security Groups and Network ACLs:** Stateful and stateless firewalls enforcing strict traffic control.

## Architecture Diagram

![AWS Secure DMZ Architecture](./aws-secure-dmz-architecture.svg)

# Secure DMZ Architecture in AWS with AWS WAF

This repository contains a design and implementation example of a secure DMZ (Demilitarized Zone) architecture on AWS, incorporating AWS WAF to protect public-facing web applications.

---

## Overview

A secure DMZ provides an additional layer of security by isolating internet-facing services from internal backend resources. This project demonstrates a best-practice AWS network design to:

- Separate public and private subnets within a Virtual Private Cloud (VPC).
- Use an Application Load Balancer (ALB) to distribute incoming traffic.
- Protect the ALB with AWS Web Application Firewall (WAF) against common web attacks.
- Enable secure administrative access through a Bastion Host.
- Use NAT Gateway for outbound internet access from private resources.
- Enforce strict network traffic filtering via Security Groups and Network ACLs.

---

## Architecture Components

| Component          | Description                                                                                  |
|--------------------|----------------------------------------------------------------------------------------------|
| **VPC**            | Virtual Private Cloud isolating the environment with CIDR 10.0.0.0/16                        |
| **Public Subnet**   | Hosts ALB, Bastion Host, and Web Servers; connected to Internet Gateway                      |
| **Private Subnet**  | Contains Application Servers and Database (RDS); no direct internet access                   |
| **Internet Gateway**| Enables inbound/outbound internet traffic for public subnet                                 |
| **Application Load Balancer (ALB)** | Distributes incoming traffic to Web Servers                             |
| **AWS WAF**         | Web Application Firewall filtering malicious traffic before ALB                             |
| **Bastion Host**    | Secure jump server for admin access to private subnet resources                              |
| **NAT Gateway**     | Allows private subnet instances to initiate outbound internet connections                    |
| **Security Groups** | Stateful firewalls controlling inbound/outbound traffic at instance level                   |
| **Network ACLs**    | Stateless subnet-level traffic filtering                                                    |

---

## Traffic Flow

1. Incoming traffic from the Internet passes through the Internet Gateway.
2. Traffic is inspected and filtered by AWS WAF.
3. Allowed requests reach the Application Load Balancer.
4. ALB forwards requests to Web Servers in the public subnet.
5. Web Servers communicate securely with backend Application Servers and Database in private subnet.
6. Admin users connect via Bastion Host to securely access private subnet instances.
7. Private subnet instances use NAT Gateway for internet-bound traffic such as software updates.

---

## Diagram

![AWS Secure DMZ Architecture](./aws-secure-dmz-architecture.svg)

---

## How to Use

- Clone this repository
- Customize the architecture based on your CIDR and resource requirements
- Deploy the design using AWS CloudFormation, Terraform, or your preferred infrastructure-as-code tool
- Integrate your applications behind the ALB
- Configure AWS WAF rules to fit your security policy

---

## Benefits

- Enhances security posture by isolating external and internal resources
- Provides protection against common web vulnerabilities
- Enables controlled and secure administrative access
- Scalable and highly available web application architecture

---


---

## Contact

For questions or contributions, feel free to open an issue or submit a pull request.

---

*Created by [Your Name]*  

## Benefits

- Enhanced security with DMZ isolation and WAF filtering.
- Scalable and highly available web application deployment.
- Secure management access and controlled internet egress for private resources.

---

Feel free to clone the repo and customize this architecture for your cloud security projects!



---

## 🤝 Connect with Me

- 🔗 **LinkedIn:** [Vineeth Kumar Vedula](https://www.linkedin.com/in/vineeth-kumar-vedula-063601135/)  
- 📧 **Email:** vvk020125@gmail.com

Feel free to explore, fork, or connect. Always open to discussing network security, automation, or collaborative ideas.

---

