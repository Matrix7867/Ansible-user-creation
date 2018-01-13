# Ansible-user creation
----------

You can use this ansible-role to add your users with

 - Password based authentication with user's key copied to the target machine
 - Proper permission (sudo required or not for the user)
 - Is the user wants passwordless sudo 

For Ex: staging/inventory files consists all the IP address of stage boxes

roles/users:
----------
 - **files**: This directory contains user's SSH Keys which need to be copied to remote server.
 - **handlers**: This main.yml contains which all service needs to be start/restart/reload.
 - **meta**: This main.yml contains dependencies of the role.
 - **tasks**: This main.yml contains all the tasks needs to be performed in the remote server
 - **vars**: This main.yml contains all the variable which we'll be using in tasks/main.yml file.
---
**How to use the roles:**

*Note:* This roles will prompt for twice to ask couple of things:

	 - Does the user wants to be added in the sudo group?
		 - (yes/no) for adding the user in sudo group. By default is [no]
	 - Does the user wants passwordless authentication?
		 -  (yes/no) for the above criteria. By default is [no]
		 
   Example: 
 
	  - ansible-playbook -i staging -l reposi server.yml -e username=test-user -e passwd=test@123
This will create a user name called `test-user` with password `test@123` which will be there in the remote machine, file named as `my_password.txt` in the user's `(test-user)` home directory. 
