# fileserver

create a vars.yml file

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

## Manual stuff

ansible-playbook 01_config_realm.yml

realm join "domain"

realm list

ansible-playbook 02_create_disk.yml

ansible-playbook 03_smb_config.yml

net ads join -U administrator