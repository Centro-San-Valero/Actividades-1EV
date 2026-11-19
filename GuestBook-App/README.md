# Simple Guestbook Application
A guestbook application where visitors can leave messages

**Topics**: PHP, MySQL, AJAX, CSS, Guestbook, Web Development

## Installation Process

### AMI LINUX 2023 - Requirements
```
sudo dnf upgrade -y
sudo dnf install -y httpd git php8.3 php8.3-fpm php8.3-pdo php8.3-mysqlnd mariadb105
sudo systemctl enable --now php-fpm httpd
```
```
cd ~
git clone https://github.com/mah-shamim/simple-guestbook-application.git
cd simple-guestbook-application
sudo mkdir -p /var/www/html/guestbook
sudo cp -r index.html *.php css js /var/www/html/guestbook/
```

### Database Setup
    Create a new AWS Mariadb/MySQL in RDS.
    Import the provided `guestbook.sql` file to set up the necessary table.
   
### **Configure the Database Connection:**
   - Open the `config.php` file and update the database credentials.
   - sudo nano /var/www/html/guestbook/config.php
     ```php
     <?php
     // config.php
     $servername = "localhost";
     $username = "yourusername";
     $password = "yourpassword";
     $dbname = "guestbook_db";
     ```
     ```sh
     sudo systemctl restart php-fpm
     sudo systemctl restart httpd
      ```

### **Access the Application:r**

     http://EC2_PUBLIC_IP/guestbook/

