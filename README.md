# Ansible-user creation

You can use this ansible-role to add your users and users.pub in the specified linux boxes, which IP address you have specified in inventory files.

For Ex: staging/inventory files consists all the IP address.

```roles/users:
	files: This directory contains user's SSH Keys which need to be copied to remote server
	handlers: This main.yml contains which all service needs to be start/restart/reload 
	meta: This main.yml contains dependencies of the role
	tasks: This main.yml contains all the tasks needs to be performed in the remote server
	vars: This main.yml contains all the variable which we'll be using in tasks/main.yml file.```
  
Usage:

ansible-playbook -i staging -l test-instance server.yml -e username=test-user -e key=test-user.pub 

staging folder contains --> Inventory of stage machine 

