# X-UI basic

simple yet usefull instruction for deploying x-ui to use websocket, tcp, kcp to bypass restricted networks.

## Deployment
Get your server up to date
```bash
apt update && apt upgrade -y
```

Also install curl and socat:
```bash
apt install curl socat -y
```
Install Acme Script

Download and install the Acme script for getting a free SSL certificate:

```bash
curl https://get.acme.sh | sh
```

Get Free SSL Certificate
Set the default provider to Let’s Encrypt:

```bash
~/.acme.sh/acme.sh --set-default-ca --server letsencrypt
```

Register your account for a free SSL certificate. In the next command, replace xxxx@xxxx.com by your actual email address:

```bash
~/.acme.sh/acme.sh --register-account -m xxxx@xxxx.com
```

Obtain an SSL certificate. In the next command, replace host.mydomain.com by your actual host name:

```bash

~/.acme.sh/acme.sh --issue -d host.mydomain.com --standalone
```

After a minute or so, the script terminates. On success, you will receive feedback as to the location of the certificate and key:
```bash

Your cert is in: /root/.acme.sh/host.mydomain.com/host.mydomain.com.cer
```
```bash

Your cert key is in: /root/.acme.sh/host.mydomain.com/host.mydomain.com.key
```

Run the X-UI Install Script
Download and run the one-click install script provided by the developer:
```bash
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```
## Config x-ui with domain

once you deployed x-ui you should be able to login with your server ip address and port 54321 (you can change the port later)

!!!For better security you can turn on firewall
```bash 
sudo ufw enable
```
## HINTS 
```
To buy domain you can use https://godaddy.com

1-dont use persian domain store!!!

2-check the ping of the server on each isp may differ (DONT 
HAVE PACKET LOSS)

3-Use https://check-host.net to check if your server and ip is clean 

4-dont use the main (make sub-domains)
```
## Protocol combinations 
these are the verified combinations that are working and its better to use them
```
1- vless + websocket 
2- vmess + websocket (lower security)
3- vless + tcp (direct without domain)
```
