---
description: nodejs installation on the server in the easiest way is following
---

# Nodejs

sudo apt update -y && sudo apt upgrade -y

sudo apt install npm -y

sudo npm i -g n

n install latest

node -v



nodejs and npm installed



## PM2

sudo npm i -g pm2

### server a express app using pm2





```
sudo pm2 start npm --  start
```

```
sudo pm2 start --name "nftblog-backend" "server.js" 
```

```javascript
sudo pm2 --name "nftblog-front" serve --spa dist 3300
```

