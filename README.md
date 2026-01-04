# WordPress eCommerce Deployment on AWS (DevOps Project)

This project demonstrates a real-world DevOps-style deployment of a **WordPress eCommerce website** on **AWS EC2**.  
The goal of this project is to understand how a web application is deployed, configured, secured, and maintained on cloud infrastructure using Linux.

---

## 🌐 Live Demo
🔗 https://wp.mdishaq.site

---

## 🧠 Project Objective

- Learn cloud infrastructure using AWS EC2
- Practice Linux server administration
- Deploy and configure a full web application
- Understand Apache, PHP, MySQL integration
- Configure DNS, SSL, and web security
- Gain hands-on DevOps experience

---

## 🏗️ Architecture Overview

- **Cloud Provider:** AWS
- **Compute:** EC2 (t2.micro)
- **OS:** Ubuntu 22.04 LTS
- **Web Server:** Apache2
- **Database:** MySQL (Local)
- **Application:** WordPress (eCommerce Theme)
- **Domain & DNS:** Cloudflare
- **SSL:** Let’s Encrypt (Certbot)

---

## 🧰 Technologies Used

- AWS EC2
- Ubuntu Linux
- Apache2
- PHP
- MySQL
- WordPress
- Cloudflare
- Certbot (HTTPS)

---

## ⚙️ Deployment Steps (High Level)

1. Launch an EC2 instance with Ubuntu 22.04
2. Configure Security Groups (Ports 22, 80, 443)
3. Install and start Apache web server
4. Install PHP and required extensions
5. Install and configure MySQL database
6. Download and configure WordPress
7. Fix file permissions and ownership
8. Configure `.htaccess` and permalinks
9. Map domain using Cloudflare DNS
10. Enable HTTPS using Certbot
11. Test and troubleshoot application

---

## 🛠️ Key Configuration Details

### Apache & PHP
- Enabled `mod_rewrite` for WordPress permalinks
- Verified Apache listening on port 80
- Restarted services after configuration changes

### WordPress
- Moved WordPress from `/wordpress` to root domain
- Fixed redirect and login issues
- Updated `wp-config.php` for site URLs
- Configured clean URLs and permalinks

### Database
- Created dedicated MySQL database and user
- Used least-privilege access model
- Connected WordPress securely to MySQL

---

## 🔐 Security & Optimization

- Enabled HTTPS with Let’s Encrypt (Certbot)
- Used Cloudflare for DNS, proxy, and security
- Proper file permissions for WordPress
- Limited server exposure via Security Groups

---

## 🧪 Troubleshooting & Learning

- Fixed DNS resolution issues
- Solved WordPress login and redirect problems
- Debugged `.htaccess` rewrite rules
- Understood Apache–WordPress request flow
- Learned importance of service restarts

---

## 🎯 Learning Outcomes

- Practical AWS EC2 management
- Linux server configuration
- Web server and database integration
- Real-world DevOps troubleshooting
- Secure and production-ready deployment
- Confidence working with live systems

---

## 📌 Future Improvements

- Automate setup using Bash or Ansible
- Use Docker for containerized deployment
- Add monitoring (CloudWatch / Prometheus)
- Implement CI/CD pipeline
- Separate database into RDS

---

## 👤 Author

**Ishaq**  
Aspiring DevOps Engineer  
GitHub: https://github.com/your-username  

---

## 📄 License

This project is licensed under the MIT License.

