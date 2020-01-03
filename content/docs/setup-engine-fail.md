+++
title = 'Installation fails on "Setup engine"'
date = 2020-01-02
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
weight = 42

[menu.docs]
  parent = "troubleshooting"
  weight = 42
+++
### Complete error message
```
TASK [uc-engine : Setup engine] *****************************************************************************************************
fatal: [localhost]: FAILED! => {"changed": false, "connection": "close", "content": "<html>\r\n<head><title>504 Gateway Time-out</tit
le></head>\r\n<body bgcolor=\"white\">\r\n<center><h1>504 Gateway Time-out</h1></center>\r\n<hr><center>nginx/1.14.2</center>\r\n</bo
dy>\r\n</html>\r\n", "content_length": "183", "content_type": "text/html", "date": "Mon, 30 Dec 2019 21:39:29 GMT", "msg": "Status co
de was 504 and not [201]: HTTP Error 504: Gateway Time-out", "redirected": false, "server": "nginx/1.14.2", "status": 504, "url": "ht
tps://localhost:443/api/setupd/1.0/setup"}
```
### Possible cause
The write speed of the sd card is too slow is a bit slow

### Resolution
#### 1. Increase nginx timeout

Override the default config
```
# cat > /etc/nginx/conf.d/sparrow.conf <<EOF
proxy_connect_timeout 600;
proxy_send_timeout 600;
proxy_read_timeout 600;
send_timeout 600;
EOF
```
Reload nginx
```
# service nginx reload
```

#### 2. Increase wazo-setupd timeout

Override the default config
```
# cat > /etc/wazo-setupd/conf.d/sparrow.yml <<EOF
auth:
  timeout: 30
confd:
  timeout: 30
sysconfd:
  timeout: 30
EOF
```
Restart the service
```
# service wazo-setupd restart
```
#### 3. Remove the half done configuration of wazo-provd
```
# rm -Rf /var/lib/wazo-provd/jsondb
```
Restart the service
```
# service wazo-provd restart
```
#### 4. Remove the half done configuration of wazo-auth
```
# wazo-auth-cli user delete root
```
Restart the service
```
# service wazo-provd restart
```
#### 5. Start the installation again
```
# ansible-playbook -i inventories/uc-engine uc-engine.yml
```
