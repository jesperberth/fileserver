# fileserver

# Install

dnf install python3-virtualenv git -y

virtualenv ansible

source ansible/bin/activate

pip install ansible

git clone https://github.com/jesperberth/fileserver.git

create a vars.yml file

vi ~/vars.yml

```yaml
---
activedirectorydomain: "domain.local"
activedirectorydomainshort: "domain"
activedirectorydomainCAP: "DOMAIN.LOCAL"
activedirectorydomainCAPshort: "DOMAIN"
domaincontroller: "dc01.domain.local"
ipallow: "192.168.130."
device: "/dev/sdb"
sharename: "share"
sharepath: "/mnt/share"
accessgroup: "sg-access-share-rw"
```
## Run

ansible-playbook 01_install_packages.yml

ansible-playbook 02_create_disk.yml

ansible-playbook 03_smb_config.yml

realm join "domain"

realm list

net ads join -U administrator

ansible-playbook 04_smb_config.yml