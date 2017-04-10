title: How To Setup RHEVM
thumbnail: /img/blog.png
date: 2015-06-20 20:23:26
tags: oVirt
---

## Prerequisites:

1. yum based system, e.g.: 
    - RHEL
    - Fedora
    - CentOS

2. Host can be either real hardware or virtual machine, but at least shoule met follow configuration:
    - 2GB RAM
    - 40GB DISK
    - internet access

<!--more-->

## Steps:

- Make a yum repo file under `/etc/yum.repo.d/`
    
	    # /etc/yum.repo.d/rhevm.repo
	    [jboss]
	    name=jboss
	    baseurl= # jboss repo url
	    enabled=1
	    gpgcheck=0

	    [rhevm]
	    name=rhevm
	    baseurl= # rhevm repo url
	    enabled=1
	    gpgcheck=0
    

- Run `yum install rhevm` if step-1 success

- Run `rhevm-setup` if step-2 success