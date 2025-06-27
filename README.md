# Simple Cloud
A simple self-hosted cloud solution with Docker and amazing Open Source Software

## Featured Software
- [filebrowser](https://github.com/filebrowser/filebrowser)
- [memo](https://github.com/usememo/usememo)

## Installation
- Install certbot on host machine
```sh
sudo apt update && sudo apt install certbot -y
```

- Create web root folder for ACME challenges
```sh
sudo mkdir -p /var/www/certbot
sudo chown -R www-data:www-data /var/www/certbot
```

- Run certbot to get certificates
```sh
sudo certbot certonly --webroot \
  --webroot-path /var/www/certbot \
  -d file.mydomain.com \
  -d notes.mydomain.com
```

- Enable auto renewal
```sh
sudo crontab -e
```
```
0 2 * * * certbot renew --quiet --webroot -w /var/www/certbot && docker restart nginx-proxy
```
