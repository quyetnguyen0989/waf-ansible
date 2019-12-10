Role Name
=========

This role can be used to configure and manage Barracuda WAF Instances. One or more Barracuda WAF instances can be managed at the same time..


Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.
1. Modules to be installed:
	ansible==2.9.2
	certifi==2019.11.28
	cffi==1.13.2
	chardet==3.0.4
	cryptography==2.8
	http-basic-auth==1.2.0
	idna==2.8
	Jinja2==2.10.3
	MarkupSafe==1.1.1
	pkg-resources==0.0.0
	pycparser==2.19
	PyYAML==5.2
	requests==2.22.0
	six==1.13.0
	urllib3==1.25.7
To install all these modules, the best option would be to copy the module names into a requirements.txt file. And then run pip install -requirement requirements.txt.

2. Create a wafcreds.json file:
Place a file called wafcreds.json in the location from where the playbook will be run. Format should be as follows:
```
{
"waf1":
    {
    "waf_ip":"<waf ip address for management>",
    "waf_port":"< management port number>",
    "waf_admin":"<api-user>",
    "waf_password":"<api-password>",
    "secure": "no"
    }
}
```
The wafcreds.json can have multiple waf entries. This is useful if you would like to configure multiple waf instances at the same time.
Note: 
	a. Please make sure that the wafcreds.json is a valid JSON document.
	b. No additional keys other than specified in the sample above are supported.
	c. All the keys in the sample are mandatory keys in wafcreds.json

3. Create a "logs" directory in the location from where the playbook will be run, for debugging the underlying API calls.

Dependencies
------------

Tested with Python 3. 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

Examples for the ansible playbooks for Barracuda WAF can be found in the examples directory.

License
-------

BSD

Author Information
------------------

Aravindan Anandan (aravindan@barracuda.com)
