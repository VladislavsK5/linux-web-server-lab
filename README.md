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
- Linux Command Line

---

# 1. Update the system
```bash
sudo apt update
sudo apt upgrade
```

### Screenshot

![System Update](<img width="1158" height="334" alt="image" src="https://github.com/user-attachments/assets/043eaa5e-9b1f-4e1f-87be-292156213668" />
)

---
# 2. Install Apache

Install the Apache web server.

```bash
sudo apt install apache2
```

Verify Apache version.

```bash
apache2 -v
```

### Screenshot

![Apache Install](<img width="644" height="132" alt="image" src="https://github.com/user-attachments/assets/66432f0a-f4eb-468f-ba3f-01cd045aa529" />
)

![Apache Version](<img width="334" height="50" alt="image" src="https://github.com/user-attachments/assets/0c64640e-180d-4200-9148-92468f227b2c" />
)

---

# 3. Verify HTTP

Find the server IP.

```bash
ip addr show
```

Open the default Apache page.

```
http://SERVER_IP (in my case 192.168.27.167)
```

### Screenshot

![Apache Default Page](<img width="644" height="339" alt="image" src="https://github.com/user-attachments/assets/c89d96bc-f321-41fc-bcd7-5cf16072b0c8" />)


---


# 4. Configure HTTPS

Enable SSL.

```bash
sudo a2enmod ssl
sudo a2ensite default-ssl
sudo systemctl restart apache2
```

### Screenshot

![Enable SSL](<img width="628" height="192" alt="image" src="https://github.com/user-attachments/assets/28a9cba6-272a-4881-b71b-047418487490" />)

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

![MySQL](<img width="644" height="163" alt="image" src="https://github.com/user-attachments/assets/41e18d00-2020-467f-a4d1-7ec807cb8fab" />
![MySQL Version](<img width="524" height="32" alt="image" src="https://github.com/user-attachments/assets/94732bf4-352a-441b-88b4-b256db468e1f" />
)

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

![Hosts](<img width="383" height="28" alt="image" src="https://github.com/user-attachments/assets/680050d0-3899-443e-ad47-42d42c7979ec" />
<img width="643" height="45" alt="image" src="https://github.com/user-attachments/assets/df1eb429-4c5e-4ab2-b568-a5085d563631" />
)

![Ping](<img width="631" height="144" alt="image" src="https://github.com/user-attachments/assets/0abd5119-0207-419f-8eef-ae7bab1ac0f8" />
)

---

# 7. Create Website 1

Create the directory.

```bash
sudo mkdir /var/www/site1
```

Create index.html.

### Screenshot

![Site1](<img width="625" height="177" alt="image" src="https://github.com/user-attachments/assets/b0945aa7-0e37-4737-aaa3-357dcb4d2adb" />
)

---

# 8. Benchmark Website 1

```bash
ab -n 1000 -c 10 http://192.168.27.167/site1/
```

### Screenshot

![Benchmark](<img width="643" height="668" alt="image" src="https://github.com/user-attachments/assets/cf97a235-09c2-4d1d-8662-1e4d246b4742" />
)

---

# 9. Create Website 2

Create

```bash
sudo mkdir /var/www/site2
```

Create another HTML page.

### Screenshot

![Site2](<img width="548" height="156" alt="image" src="https://github.com/user-attachments/assets/fe0e8e9d-67e2-4a0e-8d77-20f5c66d0abc" />
)

---
# 10. Benchmark Website 2

```bash
ab -n 1000 -c 10 http://192.168.27.167/site2/
```

### Screenshot

![Benchmark](<img width="596" height="359" alt="image" src="https://github.com/user-attachments/assets/75c0ece6-d3ac-4e16-9689-b0a1aa307f02" />
)

---


# Skills Demonstrated

- Linux Administration
- Apache Configuration
- HTTPS Configuration
- MySQL Installation
- DNS Configuration
- Apache Benchmark
- Linux CLI
