# Simple Guestbook Application
A guestbook application where visitors can leave messages

**Topics**: PHP, MySQL, AJAX, CSS, Guestbook, Web Development

## Arquitectura en AWS

![alt text](Architectura.png)


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
  
```
     mysql -h TU_ENDPOINT_RDS -P 3306 -u TU_USUARIO_RDS -p < guestbook.sql
```

   
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
     ```sh
     http://EC2_PUBLIC_IP/guestbook/
     ```

**Test App**
```sh
curl -i --max-time 15 \
  --data-urlencode "name=Prueba" \
  --data-urlencode "message=Prueba desde EC2" \
  http://127.0.0.1/guestbook/submit.php
```

### File Structure

Here’s a basic file structure for your to-do list application:

```
simple-guestbook-application/
├── config.php
├── db.php
├── index.php
├── submit.php
├── fetch.php
├── css/
│   └── style.css
├── guestbook.sql
└── js/
    └── main.js
```
## Monolith - Install mariadb in EC2
```
sudo dnf install -y mariadb105-server
sudo systemctl enable --now mariadb
sudo systemctl status mariadb --no-pager
sudo mariadb
```   
```
CREATE DATABASE guestbook CHARACTER SET utf8mb4;

CREATE USER 'guestbook'@'localhost' IDENTIFIED BY 'UnaClaveSegura_2026!';
GRANT ALL PRIVILEGES ON guestbook.* TO 'guestbook'@'localhost';
FLUSH PRIVILEGES;
``` 
