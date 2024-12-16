# Linux OS Hardening

## Objective

The goal of this project is to secure a Red Hat-based Linux server environment by implementing industry-standard best practices for system hardening. The focus is on configuring security settings to protect against potential vulnerabilities and unauthorized access, thus enhancing the overall security posture of the server.

## Skills Learned

- In-depth knowledge of Linux system hardening techniques and methodologies.
- Proficiency in configuring firewall rules using iptables and firewalld.
- Ability to implement and manage SELinux policies for enhanced security.
- Experience in securing SSH access through key-based authentication and configuration adjustments.
- Enhanced understanding of user account management, including the principle of least privilege and password policies.

## Tools Used

- Red Hat-based Linux operating system for the server environment.
- Firewall management tools (iptables and firewalld) for network traffic control.
- SELinux for mandatory access control enforcement.
- OpenSSH for secure remote login and management.

## Steps

### 1. System Updates

- Regularly update the OS packages to ensure all security patches are applied. Use the following command:
  ```bash
  sudo yum update -y
  ```
  - This command updates all installed packages to their latest available versions.

---

### 2. Firewall Configuration

- Configure firewalld to allow only necessary ports and services, minimizing potential attack vectors. For example, to allow SSH (port 22) and HTTP (port 80), use:
  ```bash
  sudo firewall-cmd --zone=public --add-service=ssh --permanent
  sudo firewall-cmd --zone=public --add-service=http --permanent
  sudo firewall-cmd --reload
  ```
  - This restricts traffic to only those services that are essential for the server's operation.

---

### 3. SELinux Setup

- Enable SELinux in enforcing mode and configure context for various applications. Use the following commands:
  ```bash
  sudo setenforce 1 sudo sed -i 's/^SELINUX=.*/SELINUX=enforcing/' /etc/selinux/config
  ```
- To check the current SELinux status, use:
  ```bash
  sestatus
  ```
  - This ensures that SELinux is actively enforcing access controls on your server.

### 4. SSH Hardening

- Implement key-based authentication and disable root login via SSH. First, generate an SSH key pair on your client machine:
  ```bash
  ssh-keygen -t rsa -b 4096
  ```
- Then copy the public key to the server:
  ```bash
  ssh-copy-id user@your-server-ip
- Next, edit the SSH configuration file:
  ```bash
  sudo nano /etc/ssh/sshd_config
- Make sure to set the following parameters:
  ```bash
  PermitRootLogin no
  PasswordAuthentication no
- Finally, restart the SSH service:
  ```bash
  sudo systemctl restart sshd
  ```
  - This enhances remote access security by requiring key-based authentication.

---

### 5. User Account Management

- Review user accounts and apply the principle of least privilege. Use the following commands to list users and their groups:
  ```bash
  cut -d: -f1 /etc/passwd
- For each user, ensure they have appropriate permissions. You can modify user groups with:
  ```bash
  sudo usermod -aG groupname username
- Implement strong password policies by editing `/etc/login.defs` and `/etc/pam.d/system-auth`.

## Conclusion

The Linux OS Hardening project provided valuable insights into securing server environments against potential threats. Through the implementation of best practices and security measures, I gained hands-on experience in several key areas:

- System Hardening: Effectively hardening a Linux server by applying security updates, configuring firewalls, and managing user accounts significantly reduces the attack surface.
- Access Control: Emphasized the importance of robust access control mechanisms, including SELinux and SSH key-based authentication, safeguarding sensitive data and system integrity.
- Networking Security: Developed a deeper understanding of network security practices through firewall configuration to manage and restrict network traffic effectively.

Overall, this project not only enhanced my technical skills but also reinforced the significance of a proactive approach to cybersecurity, equipping me with the knowledge and experience needed to protect systems against evolving threats in the cybersecurity landscape.
