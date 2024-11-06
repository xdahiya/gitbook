---
description: how to setup nginx in the ubunut server
---

# Nginx

sudo apt install nginx -y

### Popular Nginx commands[#](https://www.keycdn.com/support/nginx-commands#popular-nginx-commands) <a href="#popular-nginx-commands" id="popular-nginx-commands"></a>

Reference the following list of popular commands if you ever need a quick reminder on how to use a certain command or what it does. Remember, if you aren't a root user, you'll need to `sudo` each command in order for them to properly work.

#### Start Nginx[#](https://www.keycdn.com/support/nginx-commands#start-nginx) <a href="#start-nginx" id="start-nginx"></a>

Starting Nginx is very simple. Just use the following command:

```none
sudo service nginx start
sudo systemctl start nginx
```

#### Stop Nginx[#](https://www.keycdn.com/support/nginx-commands#stop-nginx) <a href="#stop-nginx" id="stop-nginx"></a>

Stopping Nginx will kill all system processes quickly. This will terminate Nginx even if there are open connections. In order to do so, run one of the following commands:

```none
service nginx stop
systemctl stop nginx
```

**Example response:**

```none
killall -9 nginx
```

#### Quit Nginx[#](https://www.keycdn.com/support/nginx-commands#quit-nginx) <a href="#quit-nginx" id="quit-nginx"></a>

Quitting Nginx is very similar to stopping it however it does so gracefully which means it will finish serving open connections before shutting down. To quit Nginx, use one of the following commands:

```none
systemctl quit nginx
```

#### Restart Nginx[#](https://www.keycdn.com/support/nginx-commands#restart-nginx) <a href="#restart-nginx" id="restart-nginx"></a>

```none
service nginx restart
systemctl restart nginx
```

**Example response:**

```none
Stopping nginx Server... [ OK ]
Starting nginx Server... [ OK ]
```

#### Reload Nginx[#](https://www.keycdn.com/support/nginx-commands#reload-nginx) <a href="#reload-nginx" id="reload-nginx"></a>

Reload is a bit different from restart in that, again, it is more gracefully. According to Nginx, reload is defined as "start the new worker process with a new configuration, gracefully shut down old worker processes.". You can reload Nginx by using one of the following commands:

```none
service nginx reload
systemctl reload nginx
```

**Example response:**

```none
Reloading nginx Server... [ OK ]
```

#### View server status[#](https://www.keycdn.com/support/nginx-commands#view-server-status) <a href="#view-server-status" id="view-server-status"></a>

Check what the current status of your Nginx web server is with one of the following commands:

```none
service nginx status
systemctl status nginx
```

#### Test Nginx configuration[#](https://www.keycdn.com/support/nginx-commands#test-nginx-configuration) <a href="#test-nginx-configuration" id="test-nginx-configuration"></a>

You can test your Nginx server's configuration file before restarting or reloading it completely. This helps prevent any unforeseen errors which can cause your website to gown down. To do this there are two separate commands you can use, both return the same information:

```none
nginx -t
```

Or use one of the following:

```none
service nginx configtest
systemctl config nginx
```



## nginx-setup



setup with simple backend



sudo nano /etc/nginx/sites-available/orderservice

```
upstream orderservice { server 127.0.0.1:5503; }
server { 
listen 80; 
server_name mernspace-order-service.xdahiya.loseyourip.com;
location / {
    proxy_pass http://orderservice;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_http_version 1.1;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
}
}
```

<mark style="color:yellow;">sudo ln -s /etc/nginx/sites-available/orderservice /etc/nginx/sites-enabled/orderservice</mark>

<mark style="color:yellow;">sudo systemctl restart nginx</mark>

<mark style="color:yellow;">sudo systemctl reload nginx</mark>





setup with both frontend and backend

sudo nano /etc/nginx/sites-available/code-server



```
upstream frontend { server 127.0.0.1:3000; }
upstream backend { server 127.0.0.1:3001; }
server { listen 80; server_name domain1.com;

location / {
    proxy_pass http://backend;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_http_version 1.1;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
}
}
```





```
server { listen 80; server_name domain2.com;

location / {
    proxy_pass http://frontend;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_http_version 1.1;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
}
}
```



sudo nginx -t sudo ln -s /etc/nginx/sites-available/code-server /etc/nginx/sites-enabled/code-server sudo systemctl restart nginx sudo systemctl reload nginx





## CERTBOT AND SSL

sudo apt install certbot python3-certbot-nginx

sudo certbot --nginx -d example.com -d www.example.com

sudo certbot renew --dry-run



all set



