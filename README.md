# Linux Web Server Lab

## Overview

This project demonstrates the deployment and configuration of a Linux web server using Apache, MySQL, DNS, and HTTPS on Ubuntu Server.

---

## Technologies

- Ubuntu Server
- Apache 2.4
- MySQL 8
- DNS
- HTTPS
- VirtualBox
- Linux CommandLine

---

# 1. Update the system

Update package repositories.

```bash
sudo apt update
sudo apt upgrade
```

### Screenshot

![System Update](screenshots/01-system-update.png)

---

# 2. Install Apache

Install the Apache web server.

```bash
sudo apt install apache2
```

Verify installation.

```bash
apache2 -v
```

### Screenshot

![Apache Install](screenshots/02-apache-install.png)

![Apache Version](screenshots/03-apache-version.png)

---

# 3. Verify HTTP

Find the server IP.

```bash
ip addr
```

Open the default Apache page.

```
http://SERVER_IP
```

### Screenshot

![Apache Default Page](screenshots/04-default-page.png)

---

# 4. Configure HTTPS

Enable SSL.

```bash
sudo a2enmod ssl
sudo a2ensite default-ssl
sudo systemctl restart apache2
```

### Screenshot

![Enable SSL](screenshots/05-enable-ssl.png)

---

# 5. Install MySQL

```bash
sudo apt install mysql-server
```

Verify installation.

```bash
mysql --version
```

### Screenshot
![MySQL](screenshots/06-mysql-inst.png)
![MySQL](screenshots/07-mysql-version.png)

---

# 6. Configure Local DNS

Edit the hosts file.

```bash
sudo nano /etc/hosts
```

Add

```text
192.168.27.167 vk25064.local
```

Verify.

```bash
ping vk25064.local
```

### Screenshots

![Hosts](screenshots/08-dns-hosts.png)

![Ping](screenshots/09-dns-ping.png)

---

# 7. Create Website 1

Create the directory.

```bash
sudo mkdir /var/www/site1
```

Create index.html.

### Screenshot

![Site1](screenshots/10-site1.png)

---

# 8. Benchmark Website 1

```bash
ab -n 1000 -c 10 http://192.168.27.167/site1/
```

### Screenshot

![Benchmark](screenshots/11-site1-benchmark.png)

---

# 9. Create Website 2

Create

```bash
sudo mkdir /var/www/site2
```

Create another HTML page.

### Screenshot

![Site2](screenshots/12-site2.png)

---

# 10. Benchmark Website 2

```bash
ab -n 1000 -c 10 http://192.168.27.167/site2/
```

### Screenshot

![Benchmark](screenshots/13-site2-benchmark.png)

---

# Skills Demonstrated

- Linux Administration
- Apache Configuration
- HTTPS Configuration
- MySQL Installation
- DNS Configuration
- Apache Benchmark
- Linux CommandLine
