---
layout: post
title:  "Install Python with Ansible"
date:   2019-04-21 19:28 -0500
categories: blog update ansible python
---

So you're setting up some new Ansible hosts, but after the servers come up, you get the following;

8leggedGoat | FAILED! => {
    "changed": false,
    "module_stderr": "Shared connection to 8leggedGoat closed.\r\n",
    "module_stdout": "/bin/sh: 1: /usr/bin/python: not found\r\n",
    "msg": "MODULE FAILURE",
    "rc": 127


By default, Ansible uses Python 2.7. This also means your target host needs to have Python installed
for Ansible to work. Unfortunately for us, Python is not installed by default in Ubuntu. There is
a trick we can use to bypass this shortcoming allowing Ansible to install Python on the remote hosts
using the 'raw' module as follows;

ansible -i hosts all --sudo -m raw -a "apt install -y python-minimal python-simplejson"

For more information on the 'raw' module: [Ansible - Raw Module ](https://docs.ansible.com/ansible/latest/modules/raw_module.html)
