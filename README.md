superlists-deploy-tools
=========

Requirements
------------

#### For local deployment
* virtualbox
* vagrant

#### For remote deployment
* ansible - http://docs.ansible.com/intro_installation.html

Note: I highly recommend reading the deployment chapter from TDD by Harry Percival because this is mostly his code and his book explains everything.
http://chimera.labs.oreilly.com/books/1234000000754/ch08.html

Provisioning and Deploying Superlists
-------------------------------------

#### Locally provisioning a vagrant virtualbox VM

```sh
git clone https://github.com/welenofsky/superlists-deploy-tools
cd superlists-deploy-tools
vagrant up
```

Now you can see the superlists source code in the sites folder in the current directory where you executed vagrant up.

** Provisioning a remote Ubuntu server **

If you have a Ubuntu 12.04 - 14.04 server with a domain name then you can use the ansible or fabric provisioning script at your discretion. Just make sure to edit the ansible inventory file (ansible.inventory) and specify your domain name and username used for ssh in the appropriate places.

Ansible deployment
```sh
ansible-playbook -i ansible.inventory provision.ansible.yaml --limit=live
```
