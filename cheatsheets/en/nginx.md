# Essential Nginx Commands

This document contains a list of essential commands for managing your Nginx server effectively.

---

## 📌 1. Nginx Service Management

### Start Nginx

To start the Nginx service:

```bash
sudo systemctl start nginx
```

### Stop Nginx

To stop the Nginx service:

```bash
sudo systemctl stop nginx
```

### Restart Nginx

To restart the Nginx service (useful after configuration changes):

```bash
sudo systemctl restart nginx
```

### Reload Nginx Configuration

To reload the configuration without interrupting active connections:

```bash
sudo systemctl reload nginx
```

### Check Nginx Status

To check if Nginx is running:

```bash
sudo systemctl status nginx
```

---

## ⚙ 2. Nginx Configuration

### Test Configuration Before Applying

Before restarting Nginx, verify that the configuration is correct:

```bash
sudo nginx -t
```

### Configuration File Location

The main Nginx configuration file is usually located at:

```bash
/etc/nginx/nginx.conf
```

Other configurations may be located in:

```bash
/etc/nginx/sites-available/
/etc/nginx/sites-enabled/
```

---

## 🔥 3. Log Management

### Access Access Logs

To view the access logs:

```bash
tail -f /var/log/nginx/access.log
```

### Access Error Logs

To view the error logs:

```bash
tail -f /var/log/nginx/error.log
```

---

## 🌐 4. Working with Virtual Hosts

### Create a New Virtual Host

1.  Create a new configuration file:

```bash
sudo nano /etc/nginx/sites-available/mysite
```

2.  Add the basic configuration:

```nginx
server {
    listen 80;
    server_name mysite.com;
    root /var/www/mysite;
    index index.html;
}
```

3.  Create a symbolic link to activate the site:

```bash
sudo ln -s /etc/nginx/sites-available/mysite /etc/nginx/sites-enabled/
```

4.  Test the configuration and restart Nginx:

```bash
sudo nginx -t
sudo systemctl restart nginx
```

---

## 🧹 5. Cleanup and Maintenance

### Remove Unnecessary Nginx Packages

```bash
sudo apt autoremove nginx
```

### Stop and Disable Nginx on Boot

```bash
sudo systemctl disable nginx
```
