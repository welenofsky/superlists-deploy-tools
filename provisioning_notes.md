Provisioning a new site
=======================

## Required Packages

* nginx
* Python 3
* Git
* pip
* virtualenv

eg, on Ubuntu:
  sudo apt-get install nginx git python3 python3-pip
  sudo pip3 install virtualenv

## Nginx Virtual Host config

* see nginx.template.conf
* replace SITENAME and USER with, eg, ubuntu and staging.my-domain.com

## Upstart Job

* see gunicorn-upstart.template.conf
* replace SITENAME and USER with, eg, ubuntu and staging.my-domain.com

## Folder structure
Assume we have a user account at /home/username
/home/username
└── sites
    └── SITENAME
        ├── database
	├── source
	├── static
	└── virtualenv


Using the ansible deployments/provisioning script
=================================================

## Required Packages

* VMWare (If you are using jwele/trusty64)
* Vagrant
* ansible

## Setting Up Local Environment

1. Get Vagrant+VMWare

2. pip install ansible

    pip install ansible

3. Vagrant up

	cd /path/to/thisfolder && vagrant up

Vagrant is set to by default provision. you may also provision at a later time with the ansible-playbook command

    ansible-playbook -i ansible.inventory provision.ansible.yaml --limit=local --private-key=~/.vagrant.d/insecure_private_key

