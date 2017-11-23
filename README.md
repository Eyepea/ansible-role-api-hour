eyepea.api-hour
========

[![Build Status](https://travis-ci.org/Eyepea/ansible-role-api-hour.svg?branch=master)](https://travis-ci.org/Eyepea/ansible-role-api-hour)

Ansible role to install and configure an [API-Hour](https://github.com/Eyepea/API-Hour) daemon.

Installation
------------

To install this roles clone it into your roles directory.

```bash
$ git clone https://github.com/eyepea/ansible-role-api-hour.git eyepea.api-hour
```

If your playbook already reside inside a git repository you can clone it by using git submodules.

```bash
$ git submodule add -b master https://github.com/eyepea/ansible-role-api-hour.git eyepea.api-hour
```

Requirements
------------

The [pyslackers.python](https://github.com/pyslackers/ansible-role-python) is required to install python. Install it 
with one of these commands:

```bash
$ git clone https://github.com/pyslackers/ansible-role-python.git pyslackers.python
```

```bash
$ git submodule add -b master https://github.com/pyslackers/ansible-role-python.git pyslackers.python
```

Role Variables
--------------

* `ah_name`: Name of the daemon.
* `ah_git_url`: Git url to clone daemon.
* `ah_python_version`: Python version required for the daemon.
* `ah_version`: Version to clone (default to `master`).
* `ah_requirements_path`: Path to python requirements file (default to `requirements.txt`).
* `ah_sockets`: List of listening sockets (default to `[0.0.0.0:8000]`).

Example Playbook
----------------

```yml
- hosts: localhost
  vars:
    ah_name: api-hour-demo
    ah_git_url: https://github.com/Eyepea/api-hour-demo.git
    ah_python_version: 3.6.3
  roles:
    - eyepea.api-hour
```

License
-------

MIT
