Provisioning a new site
=======================

## Required Packages

* nginx
* Python 3
* Git
* python3-pip
* virtualenv

eg, on Ubuntu:
  sudo apt-get install nginx git python3 python3-pip
  sudo pip3 install virtualenv

## Nginx Virtual Host config

* see roles/web/templates/nginx.conf.j2
* file changes values based on staging or local deployment

## Upstart Job

* see roles/web/templates/gunicorn-upstart.conf.j2
* file changes current directory based on server. see below.

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

* Virtualbox
* Vagrant
* Ansible

## Setting Up Local Environment

1. Get Vagrant+Virtualbox

2. pip install ansible

    pip install ansible

3. Vagrant up

	cd /path/to/thisfolder && vagrant up

Vagrant is set to by default provision. you may also provision at a later time with the ansible-playbook command.

    ansible-playbook -i production site.yml --private-key=~/.vagrant.d/insecure_private_key

More examples at:
  http://docs.ansible.com/ansible/playbooks_best_practices.html#what-this-organization-enables-examples
