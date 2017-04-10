title: Ansible Note 01
thumbnail: /img/python.png
date: 2015-07-20 20:35:00
tags: [python, ansible]
---

## 1. The Ansible Configuration File

1. ansible.cfg (in the current directory)
2. ANSIBLE_CONFIG (an environment variable)
3. `.ansible.cfg` (in the home directory)
4. /etc/ansible/ansible.cfg

Ansible will process the above list and use the first file found. Settings in files are **not merged**.

<i class="fa fa-external-link"></i> [ansible.cfg with latest values](https://raw.github.com/ansible/ansible/devel/examples/ansible.cfg)



## 2. Setting the Environment (and Working With Proxies)

It is quite possible that you may need to get package updates through a proxy, or even get some package updates through a proxy and access other packages not through a proxy. Or maybe a script you might wish to call may also need certain environment variables set to run properly.

<!--more-->

```
---
- hosts: all
  remote_user: root

  tasks:

    - apt: name=cobbler state=installed
      environment:
        http_proxy: http://proxy.example.com:8080
        https_proxy: https://proxy.example.com:8090
```


## 3. Tags

If you have a large playbook it may become useful to be able to run a specific part of the configuration without running the whole playbook.

- Both plays and tasks support a “tags:” attribute for this reason.

	```
	tasks:

	    - yum: name={{ item }} state=installed
	      with_items:
	         - httpd
	         - memcached
	      tags:
	         - packages

	    - template: src=templates/src.j2 dest=/etc/foo.conf
	      tags:
	         - configuration
	```

- If you wanted to just run the “configuration” and “packages” part of a very long playbook, you could do this:

	```
	 ansible-playbook example.yml --tags "configuration,packages"
	```

- On the other hand, if you want to run a playbook without certain tasks, you could do this:

	```
	ansible-playbook example.yml --skip-tags "notification"
	```

- You may also apply tags to roles:

	```
	roles:
	  - { role: webserver, port: 5000, tags: [ 'web', 'foo' ] }
	```
