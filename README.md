# fileserver

## Manual stuff

ansible-playbook 01_config_realm.yml

realm join "domain"

realm list

ansible-playbook 02_create_disk.yml

ansible-playbook 03_smb_config.yml

net ads join -U administrator