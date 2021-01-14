# fileserver

# Install

dnf install python3-virtualenv git

virtualenv ansible

source ansible/bin/activate

pip install ansible

git clone https://github.com/jesperberth/fileserver.git

create a vars.yml file ../vars.yml

```yaml
---
activedirectorydomain: "domain.local"
activedirectorydomainshort: "domain"
activedirectorydomainCAP: "DOMAIN.LOCAL"
activedirectorydomainCAPshort: "DOMAIN"
domaincontroller: "dc01.domain.local"
device: "/dev/sdb"
sharename: "share"
sharepath: "/mnt/share"
accessgroup: "sg-access-share-rw"
```
## Run

ansible-playbook 01_config_realm.yml

realm join "domain"

realm list

ansible-playbook 02_create_disk.yml

ansible-playbook 03_smb_config.yml

net ads join -U administrator