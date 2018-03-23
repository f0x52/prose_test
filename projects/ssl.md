---
layout: default
title: ssl
permalink: /projects/ssl/
nolink: true
---

Good SSL is important for **any** site. Over time I've combined bits of other configs, giving me this setup (which also gives a perfect [ssltest](https://ssllabs/ssltest) score):  

First generate /etc/ssl/certs/dhparam.pem:  
<code>
sudo openssl dhparam -dsaparam -out /etc/ssl/certs/dhparam.pem 8192
</code>
<br>
Nginx config:
<pre><code>server {
    listen 443 ssl;
    listen [::]:443 ssl;
    server_name f.0x52.eu, 0x52.eu, www.0x52.eu;
    ssl_certificate /etc/letsencrypt/live/f.0x52.eu/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/f.0x52.eu/privkey.pem; # managed by Certbot

    ssl_dhparam /etc/ssl/certs/dhparam.pem;
    ssl_protocols TLSv1.2;
    ssl_prefer_server_ciphers on;
    ssl_ciphers AES256+EECDH:AES256+EDH:!aNULL;
    ssl_ecdh_curve secp384r1; # Requires nginx >= 1.1.0
    ssl_session_cache shared:SSL:10m;
    ssl_session_timeout 10m;

    ssl_session_tickets off; # Requires nginx >= 1.5.9
    ssl_stapling on; # Requires nginx >= 1.3.7
    ssl_stapling_verify on; # Requires nginx => 1.3.7
    resolver 87.98.175.85 5.9.49.12 193.183.98.154 5.135.183.146 valid=300s;
    resolver_timeout 5s;
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains; preload";
    add_header X-Frame-Options DENY;
    add_header X-Content-Type-Options nosniff;
    gzip off;

    root /var/www/f.0x52.eu;
}

server {
    listen 80;
    server_name f.0x52.eu, 0x52.eu, www.0x52.eu;

    location /.well-known {
        root /var/www/git.omnius.zone;
    }

    location / {
        if ($scheme != "https"){
            return 301 https://$host$request_uri;
        }
        return 404;
    }
}
</code></pre>
<br>
You'll need to comment out the 443 block before generating the first cert, otherwise nginx complains about the nonexistent cert files.<br><br>
Get letsencrypt certs:
<code>
sudo certbot --authenticator webroot --installer nginx -d f.0x52.eu -d 0x52.eu -d www.0x52.eu --rsa-key-size 4096
</code>
<br>
Remove the 443 block comments, restart nginx and all should be great!
