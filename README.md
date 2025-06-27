# Simple Cloud
A simple self-hosted cloud solution with Docker and amazing Open Source Software

## Featured Software
- [nginx-proxy-manager](TODO)

|Name               | Project Repository                         | Subdomain |
|-------------------|--------------------------------------------|-----------|
|filebrowser        | https://github.com/filebrowser/filebrowser | files     |
|memos              | https://github.com/usememos/memos          | memos     |
|nginx-proxy-manager| https://github.com/usememos/memos          |           |

## Installation
- Install docker engine
- Run `docker compose up -d`
- Setup your domain
    - Add A Record for your root domain that target your ip address
    - Add A Record for **notes** subdomain that target your ip address
    - Add A Record for **files** subdomain that target your ip address
- Go to `http://<your-ip-address>:81` to setup proxy
    - Add Proxy Hosts the domain name for each apps with following entries
        - Domain names: <subdomain>.<domain>
        - Scheme: http
        - Forward Hostname/IP: <container-name>
        - Forward Port: 80
        - Enable websocket support
        - Enable block common exploits 
    - Go to SSL tabs and generate SSL Certificate
        - Enable HTTP/2 support
        - Enable Force SSL
