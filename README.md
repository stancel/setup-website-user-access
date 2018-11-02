setup_website_user_access
=========

Ansible role that creates one or more Linux users and sets up sftp access to be able to access their website directory on a shared hosting server.

Requirements
------------

While this can be used on any Linux server, it's original and primary purpose is to be used as a specialized role in a shared webserver Ansible playbook, just setting up chrooted access to that user's website.

Role Variables
--------------

Sites to setup and host on the webserver
```
	setup_website_user_access_list:
	  - {
		  name: 'mysite',
		  user_password: 'my-secure-password'
		}
```

(Default) The document root/absolute path that is the parent of the new user's home directory. The default is "/var/www"
```
	setup_website_user_access_web_root: "/var/www"
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

	- hosts: your_server
	  vars_files:
	    - vars/main.yml
	  roles:
	    - stancel.setup_website_user_access 

or just pass the variables in the playbook

	- hosts: your_server 
	  vars:
        setup_website_user_access_list:
          - {
              name: 'mysite',
              user_password: 'my-super-secure-password'
            }
	  roles:
	    - stancel.setup_website_user_access


License
-------

GPLv3

Author Information
------------------

[Brad Stancel](https://github.com/stancel) 

