# INET 4031 – Puppet Lab 11

This repository contains the Puppet code used for Lab 11. The purpose of this lab is to use Puppet to manage users on a server and to set up a basic LAMP stack (Linux, Apache, MySQL, PHP).

## Files in This Repository

### `testing_puppet.pp`
Simple Puppet manifest used to test Puppet on the server.  
It creates a file named `/tmp/hello.txt` with sample text.

### `server_users_groups.pp`
Puppet manifest used to manage users and groups on the server.  
This file:
- Creates groups (`group01` and `group02`)
- Creates users (`user04`, `user05`, `user06`, `user07`)
- Sets correct shells, passwords (SHA-512 hashed), and group management
- Uses `managehome` to create home directories

### `lamp_stack_server.pp`
Puppet manifest that installs and configures a basic LAMP stack:
- Installs Apache2
- Installs PHP and required PHP modules  
- Creates a `phpinfo.php` test page under `/var/www/html/`
- Installs and enables the MariaDB server service

### `phpinfo.php`
A simple PHP file used to test that PHP is working on the Apache server.  
Puppet copies this file into the web root.

## How It Works
Puppet reads each manifest file and applies the desired system state.  
It installs packages, creates users, manages services, and ensures files exist exactly as defined.  
If something is missing or changed, Puppet fixes it automatically to match the code.
