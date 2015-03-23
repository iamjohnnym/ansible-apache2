# Ansible deployment for Apache2

## 0. Current Stats

[![Build Status](https://travis-ci.org/configuresystems/ansible-apache2.svg)](https://travis-ci.org/configuresystems/ansible-apache2)

|    Name         |    Description            |
| --------------- | ------------------------- |
| Version         | 0.1                       |
| Updated         | 03.22.2015                |
| Ansible Version | 1.8.4                     |
| Author          | Johnny Martin             |
| Website         | http://configure.systems/ |
| License         | MIT                       |


## 1. QuickStart

```bash
git clone https://github.com/configuresystems/ansible-jira.git roles/ansible-jira
# Create a playbook file to use, there's a sample one in tests/test.yml
# Create a group_vars or update the default values in defaults/main.yml
ansible-playbook -i path/to/inventory ansible-playbook.yml
```

    
## Table of contents

- [1. QuickStart](#1-quickstart)
- [2. Overview](#2-overview)
- [3. Requirements](#3-requirements)
  - [3.1 Ubuntu](#31-ubuntu)
  - [3.2 Compile from Source](#32-compile-from-source)
- [4. Usage](#4-usage)
  - [4.1 Playbook Arguments](#41-playbook-arguments)
- [5. After Install](#5-after-install)
- [6. Apache2 Control](#6-apache2-control)
  - [6.1 Stop](#61-stop)
  - [6.2 Start](#62-start)
  - [6.3 Restart](#63-restart)


## 2. Overview

An Ansible playbook to automate the installation of Apache2.


## 3. Requirements

Ansible installed on the local machine.

#### 3.1 Ubuntu

```bash
pip install ansible
```

#### 3.2 Compile from Source

```bash
git clone git://github.com/ansible/ansible.git --recursive
cd ./ansible
source ./hacking/env-setup
```

## 4. Usage

1. `git clone http://github.com/configuresystems/ansible-apache2`
2. Create a vars file in your group_vars, host_vars, set vars in the Playbook,
   or update the 'defaults/main.yml' file
3. run the Ansible playbook, the fastest way is:

```bash
ansible-playbook ansible-apache2.yml
```

### 4.1 Playbook Arguments

- port: Port that the virtualhost utilizes
- server_name: Domain name you wish the virtualhost to use
- server_alias: Alias the virtualhost will use
- document_root: Base directory where site files will reside
- document_owner: Owner of the document root
- document_group: Group of the document root
- ssl_crt: If using SSL, where to put the CRT file
- ssl_key: If using SSL, where to put the KEY file
- ssl_ca_chain: If using SSL, where to put the CA.CRT file
- SSL: Boolean.


### 5. After install

Assuming DNS is point to the server for the {{ server_name }}; Visit the
apache2 server via the browser by going to:

http://{{ server_name }}

Finish up the install process by adding the database info and
product key probvided by Atlassian.

### 6. Apache2 Control

#### 6.1 Stop

```bash
service apache2 stop
```

#### 6.2 Start

```bash
service apache2 start
```

#### 6.3 Restart

```bash
service apache2 restart
```
