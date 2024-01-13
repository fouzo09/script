## Installer NGINX NodeJS & NPM

```bash
sudo apt install nginx
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
```

## Installer PM2
```bash
npm install pm2
```

##Config NGINX
bash```
server {
    listen 80;
    server_name domain.com;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```
##SQL - Create table 
bash```
CREATE DATABASE IF NOT EXISTS testdb;
USE testdb;

CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    email VARCHAR(255)
);
```

##Montage de disc
bash```
lsblk
sudo file -s /dev/xvdf
sudo mkfs -t ext4 device_name
sudo mount device_name mount_point
```
