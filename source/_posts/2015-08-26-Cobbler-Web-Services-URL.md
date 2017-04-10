title: Some Cobbler Issues
thumbnail: img/linux.jpg
categories: Technical
date: 2015-08-26 14:09:33
tags: cobbler
---

## To avoid infinite PXE installation boot loop

- sent this request as the last step of installation
	```bash
	http[s]://[cobbler-server-ip]/cblr/svc/op/nopxe/system/[system name]
	```

## Remove `ipappend 2` from pxe boot menu
<!-- more -->
- Find these two files
	```bash
	/etc/cobbler/pxe/pxesystem.template
	/etc/cobbler/pxe/pxeprofile.template
	```

- Remove the line `ipappend 2`
	```bash
	default linux
	prompt 0
	timeout 1
	label linux
        kernel $kernel_path
    --> ipappend 2 <-- 
        $append_line
	```

## Cobbler-Web Issues

- if u encounter the follow error message when access `/cobbler_web`
	```
	AppRegistryNotReady at /
	Apps aren't loaded yet.
	Request Method: GET
	Request URL:    https://127.0.0.1/cobbler_web/
	Django Version: 1.8.2
	Exception Type: AppRegistryNotReady
	Exception Value:    
	Apps aren't loaded yet.
	...
	```

This solution works for me

1. check the `/usr/share/cobbler/web/cobbler.wsgi`

2. change the followed line
	```python
	_application = django.core.handlers.wsgi.WSGIHandler()
	```
3. to
	```python
	from django.core.wsgi import get_wsgi_application
	_application = get_wsgi_application()
	```