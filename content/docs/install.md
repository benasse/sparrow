+++
title = "Installation"

date = 2020-01-02
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
weight = 30
+++
## Requirements
* Your hardware runs a minimal rasbian (or equivalent), installed with UTF8 locales
* The network of this computer is correctly configured and it has internet access

## Installation

#### 1. Install required packages
```bash
apt install -y ansible git
```

#### 2. Clone repository containing ansible recipes for the installation
```bash
git clone https://github.com/benasse/wazo-ansible/
```

#### 3. Configure the application password
```bash
cd wazo-ansible
```
* Edit the file `inventories/uc-engine` with your favorite text editor
* Add the following lines at the end of the file, replacing `****` with your password
```
engine_api_configure_wizard = true
engine_api_root_password = ****
```
#### 4. Install ansible dependency
```bash
ansible-galaxy install -r requirements-postgresql.yml
```
#### 5. Install wazo-platform
```bash
ansible-playbook -i inventories/uc-engine uc-engine.yml
```
If you get an error please refer on the troubleshooting part of the documentation.

When the installation is finished, you can consult the [quick start](../quick-start) section.
