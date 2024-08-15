# Linux OS Hardening

## Objective

The Linux OS hardening project aimed to secure a Red Hat based Linux server environment by implementing industry-standard best practices for system hardening. The focus was on configuring security settings to protect against potential vulnerabilities and unauthorized access, thus enhancing the overall security posture of the server.

### Skills Learned

- In-depth knowledge of Linux system hardening techniques and methodologies.
- Proficiency in configuring firewall rules using iptables and firewalld.
- Ability to implement and manage SELinux policies for enhanced security.
- Experience in securing SSH access through key-based authentication and configuration adjustments.
- Enhanced understanding of user account management, including the principle of least privilege and password policies.

### Tools Used

- Red Hat based Linux operating system for the server environment.
- Firewall management tools (iptables and firewalld) for network traffic control.
- SELinux for mandatory access control enforcement.
- OpenSSH for secure remote login and management.

## Steps

### 1. System Updates

- Regularly updated the OS packages using yum update to ensure all security patches were applied.

System Update Screenshot
Ref 1: Terminal showing the update process


### 2. Firewall Configuration

- Configured firewalld to allow only necessary ports and services, minimizing potential attack vectors.

Firewall Configuration Screenshot
Ref 2: Firewall rules setup in a terminal


### 3. SELinux Setup

- Enabled SELinux in enforcing mode and configured context for various applications to ensure strict access controls.

SELinux Configuration Screenshot
Ref 3: SELinux status and configurations


### 4. SSH Hardening

- Implemented key-based authentication and disabled root login via SSH to enhance remote access security.

SSH Configuration Screenshot
Ref 4: SSH configuration file showing hardening steps


### 5. User Account Management

- Reviewed user accounts and applied the principle of least privilege, ensuring that users had only the necessary permissions.

User Management Screenshot
Ref 5: User account settings in terminal

## Conclusion

The Linux OS Hardening project provided valuable insights into the critical importance of securing server environments against potential threats. Through the implementation of best practices and security measures, I gained hands-on experience in several key areas:

- System Hardening: I learned how to effectively harden a Linux server by applying security updates, configuring firewalls, and managing user accounts, which significantly reduces the attack surface.
- Access Control: The project emphasized the importance of robust access control mechanisms, including the use of SELinux and SSH key-based authentication, which safeguards sensitive data and system integrity.
- Networking Security: I developed a deeper understanding of network security practices through the configuration of firewalls to manage and restrict network traffic effectively.

Overall, this project not only enhanced my technical skills but also reinforced the significance of a proactive approach to cybersecurity, equipping me with the knowledge and experience needed to protect systems against evolving threats in the cybersecurity landscape.
