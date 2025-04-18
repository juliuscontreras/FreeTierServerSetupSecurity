# Free Tier Server Setup & Security Configuration

## Part 1: Cloud Server Setup

1.  **AWS Setup:**
    * To initiate this project, I selected AWS as my cloud provider due to its robust free tier offering. [cite: 22]
    * I created a new AWS account, carefully noting the limitations imposed by the free tier, such as instance types and storage space. [cite: 23]

2.  **Instance Launch:**
    * I launched a `t2.micro` instance, opting for Ubuntu Server 22.04 LTS as the operating system. [cite: 24]
    * To enhance security, I configured a security group to allow inbound traffic only on SSH port 22. [cite: 25]

3.  **SSH Connection:**
    * I established an SSH connection to the instance using terminal on my Windows machine. [cite: 25]
    * This connection was secured with a strong SSH key pair, eliminating the need for password authentication. [cite: 26]

4.  **System Update & Web Server Installation:**
    * Once connected, I updated the system packages using `apt update && apt upgrade`. [cite: 27]
    * Subsequently, I installed the Apache2 web server using `sudo apt install apache2`. [cite: 28]
    * To verify the server's functionality, I created a simple "Hello World" HTML file in the `/var/www/html` directory. [cite: 29]

## Part 2: Server Security Configuration

1.  **SSH Security:**
    * To bolster SSH security, I accessed the `sshd_config` file and changed the following: [cite: 30, 31]
        * Disabled root login. [cite: 30, 31]
        * Changed the default SSH port to 4422. [cite: 31]
        * Configured SSH to use key-based authentication exclusively. [cite: 31]

2.  **Firewall Configuration:**
    * I installed `ufw` and configured it to: [cite: 32, 33, 34]
        * Allow incoming traffic on the non-standard SSH port (4422). [cite: 32, 33]
        * Permit HTTP (port 80) and HTTPS (port 443) traffic for the web server. [cite: 33]
        * Deny all other inbound traffic by using the default rule `ufw default deny incoming`. [cite: 34]

3.  **Intrusion Prevention:**
    * I installed Fail2Ban to automatically block IP addresses that exhibit malicious behavior, such as brute-force attacks. [cite: 35, 36, 37, 38]
    * I configured Fail2Ban to ban IPs after three failed login attempts. [cite: 36, 37, 38]

4.  **Logging:**
    * To monitor server activity, I enabled basic logging for SSH and firewall activities. [cite: 37, 38]
    * Generated three failed login attempts to show Fail2Ban banning failed login attempts. [cite: 38]

## Conclusion

This document serves as a comprehensive record of the server setup and security configurations. [cite: 39, 40, 41, 42] It details the modifications made to SSH, the firewall rules implemented, and the configuration of Fail2Ban. [cite: 39, 40, 41, 42] By following these steps, I have established a secure and functional cloud server. [cite: 41, 42] The implemented security measures significantly reduce the risk of unauthorized access and potential attacks. [cite: 41, 42]
