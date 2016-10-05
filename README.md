Role Name
=========

Installs rundeck http://rundeck.org/ role.
Also installs Ansible for executing playbooks and etc. Configurable options and Logstash plugin ready.

Requirements
------------

None

Vagrant
-------
````
vagrant up
````

Usage
-----

Open up browser of choice

Vagrant Environment
http://127.0.0.1:4440
````
user: admin
password: admin
````

Non-Vagrant Environment
http://iporhostname:4440
````
user: admin
password: admin
````

Role Variables
--------------

````
---
# defaults file for ansible-rundeck
config_rundeck: true
enable_rundeck: true
enable_rundeck_plugins: true
pri_domain_name: example.org
rundeck_base: /var/lib/rundeck
rundeck_ssh_keydir: './ssh_pub_keys/'
rundeck_configs:
  - 'framework.properties'
  - 'rundeck-config.properties'
rundeck_db_name: 'rundeck'
rundeck_db_pass: 'rundeck'
rundeck_db_user: 'rundeck'
rundeck_dl_pkg: 'rundeck-{{ rundeck_version }}-GA.deb'
rundeck_dl_url: 'http://dl.bintray.com/rundeck/rundeck-deb/'
rundeck_enable_logstash_plugin: false
rundeck_framework_server_hostname: 'localhost'
rundeck_framework_server_name: 'localhost'
rundeck_framework_server_password: 'admin'
rundeck_framework_server_port: 4440
rundeck_framework_server_url: 'http://{{ rundeck_framework_server_hostname }}'
rundeck_framework_server_username: 'admin'
rundeck_framework_ssh_keypath_file: '{{ rundeck_framework_ssh_keypath }}/id_rsa'
rundeck_framework_ssh_keypath: '/var/lib/rundeck/.ssh'
rundeck_framework_ssh_user: 'rundeck'
rundeck_install_ansible: true
rundeck_logstash_host: []  #defines logstash server if used
rundeck_logstash_port: 9700
rundeck_mysql_backend: false
rundeck_root_dir: '/etc/rundeck'
rundeck_vagrant_install: false  #defines if installing under Vagrant
rundeck_version: '2.6.9-1'
rundeck_install_ansible_version: '2.1.1.0'
````

Dependencies
------------

None.

Example Playbook
----------------

#### GitHub
````
---
- hosts: all
  become: true
  vars:
  roles:
    - role: ansible-rundeck
  tasks:
````
#### Galaxy
````
---
- hosts: all
  become: true
  vars:
  roles:
    - role: mrlesmithjr.rundeck
  tasks:
````

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com
