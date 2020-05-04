+++
title = 'Installation fails on "Create service users with wazo-auth-keys"'
date = 2020-01-02
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
weight = 71

[menu.docs]
  parent = "troubleshoot"
  weight = 71
+++
### Complete error message
```
TASK [engine-api-init : Create service users with wazo-auth-keys] *******************************************************************
fatal: [localhost]: FAILED! => {"changed": true, "cmd": ["wazo-auth-keys", "service", "update"], "delta": "0:01:02.381832", "end": "2
019-12-29 13:20:27.884293", "msg": "non-zero return code", "rc": 1, "start": "2019-12-29 13:19:25.502461", "stderr": "HTTPSConnection
Pool(host='localhost', port=9497): Read timed out. (read timeout=10)", "stderr_lines": ["HTTPSConnectionPool(host='localhost', port=9
497): Read timed out. (read timeout=10)"], "stdout": "", "stdout_lines": []}
```
### Possible cause
The write speed of the sd card is a bit slow, or your raspberry is a bit hot due to the install and under-clocks itself to cool.

### Resolution
#### 1. Increase timeout
```bash
cat > /etc/wazo-auth-cli/conf.d/sparrow.yml <<EOF
auth:
  timeout: 30
EOF
```
#### 2. Regenerate keys
```bash
wazo-auth-keys service update --recreate
```
#### 3. Start the installation again
```bash
ansible-playbook -i inventories/uc-engine uc-engine.yml
```

