# WordPress eCommerce Deployment on AWS EC2

This project demonstrates a beginner-friendly deployment of a WordPress eCommerce website on **AWS EC2** using Ubuntu 22.04, Apache, PHP, and MySQL. It’s designed to help learn **cloud hosting, Linux server setup, and WordPress deployment** in a single workflow.

---

## 🌐 Live Demo
[https://wp.mdishaq.site](https://wp.mdishaq.site)
![Live Demo](Project-Screenshot/web2.png)

---

## 🧰 Technologies Used
- **Cloud Provider:** AWS EC2 (t2.micro)
- **OS:** Ubuntu 22.04 LTS
- **Web Server:** Apache2
- **Database:** MySQL (local)
- **Application:** WordPress
- **Optional Enhancements:** HTTPS (Certbot), Cloudflare CDN

---

## ⚙️ Setup Steps

1. Launch an **EC2 instance** with Ubuntu 22.04
2. Connect via SSH
3. Install Apache2:
    ```bash
    sudo apt update
    sudo apt install apache2 -y
    sudo systemctl enable apache2
    sudo systemctl start apache2
    ```
4. Install PHP and required extensions:
    ```bash
    sudo apt install php libapache2-mod-php php-mysql php-curl php-gd php-mbstring php-xml php-zip php-intl -y
    sudo systemctl restart apache2
    ```
5. Install MySQL:
    ```bash
    sudo apt install mysql-server -y
    sudo mysql
    CREATE DATABASE Shahid;
    CREATE USER 'Shahid_new'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Shahid@123DevOps';
    GRANT ALL PRIVILEGES ON Shahid.* TO 'Shahid_new'@'localhost';
    FLUSH PRIVILEGES;
    EXIT;
    ```
6. Install WordPress:
    ```bash
    cd /tmp
    wget https://wordpress.org/latest.tar.gz
    tar -xzf latest.tar.gz
    sudo mv wordpress /var/www/html/
    sudo chown -R www-data:www-data /var/www/html
    sudo find /var/www/html -type d -exec chmod 755 {} \;
    sudo find /var/www/html -type f -exec chmod 644 {} \;
    ```
7. Configure WordPress database:
    - Edit `wp-config.php` with DB details
8. Fix `.htaccess` for root URLs and permalinks:
    ```apache
    <IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteBase /
    RewriteRule ^index\.php$ - [L]
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . /index.php [L]
    </IfModule>
    ```
9. Restart Apache:
    ```bash
    sudo systemctl restart apache2
    ```
10. Optional: Enable HTTPS using Certbot:
    ```bash
    sudo apt install certbot python3-certbot-apache -y
    sudo certbot --apache
    ```

---

## 📌 Features
- Fully functional **WordPress eCommerce site**
- Clean URLs (`https://wp.mdishaq.site`)
- Modern theme with pages: Home, Shop, Blog, Contact
- Secure HTTPS via Certbot
- Cloudflare integration

---

## 🎯 Learning Outcomes
- Deploy WordPress on **AWS EC2**
- Configure Apache, PHP, MySQL
- Move WordPress from `/wordpress` → root domain
- Fix `.htaccess` and permalinks
- Enable HTTPS and Cloudflare CDN
- Manage WordPress themes, plugins, and pages

---

## 🔧 Author
**Muhammad Ishaq**  
Cloud and DevOps enthusiast  

---

## ⚡ License
MIT License

