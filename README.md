Overview about this page.
It is a hub for ecosystem that Our team is building. Overview about our team vision and all projects in the ecosystem.
If you want to know more details about each project, you can click on one and link to the project for details.
Thank you.

How to run Hub UI.
# Setup
# Install nvm and set up enviroment
# nvm install 14
# Node version 14: nvm use 14
# npm install node-sass
# npm start


# restart server: /etc/init.d/nginx restart

# Server config
``` Ruby:
# Bsc exchange ecosystem
server {
  location / {
  root /home/bsc_exchange_ecosystem/build;
  add_header Cache-Control "private, no-store, no-cache";
  index index.html;
  error_page 404 /index.html;
  try_files $uri /index.html$is_args$args =404;
  if (!-e $request_filename){
  rewrite ^(.*)$ /index.html break;
  }
}

  listen 443 ssl http2;
  listen [::]:443 ssl http2;
  server_name hub.hocvienstock.com;
  ssl_certificate /etc/letsencrypt/live/hub.hocvienstock.com/fullchain.pem;
  ssl_certificate_key /etc/letsencrypt/live/hub.hocvienstock.com/privkey.pem;
  ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
  ssl_prefer_server_ciphers on;
  ssl_ciphers AES256+EECDH:AES256+EDH:!aNULL;
  root /home/bsc_exchange_ecosystem/build;
}
