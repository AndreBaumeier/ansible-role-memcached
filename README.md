# Ansible Role: Memcached

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-memcached.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-memcached)

An Ansible Role that installs Memcached on RedHat/CentOS or Debian/Ubuntu Linux.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    memcached_user: memcache

The user under which the Memcached daemon will run.

    memcached_port: 11211
    memcached_listen_ip: 127.0.0.1

The port and IP address (127.0.0.1 for localhost) on which Memcached will listen for requests.

    memcached_memory_limit: 64
    memcached_connections: 1024

Memcached limits. The maximum amount of RAM `memcached` will consume (64MB is the default), and the maximum number of simultaneous connections memcached will handle.

    memcached_log_file: /var/log/memcached.log

The location of the memcached log file.

    memcached_log_verbosity: ""

Normally memcached does not log anything. Change to "-v" to enable logging or to "-vv" for debug logging.

    memcached_package: memcached

The packagage name of memecached. In case different OS has different package naming.

    memcached_package_state: present
    
If you have enabled any additional repositories such as ondrej/apache2, geerlingguy.repo-epel, or geerlingguy.repo-remi, you may want an easy way to upgrade versions. You can set this to latest (combined with memcached_enablerepo on RHEL) and can directly upgrade to a different Memcached version from a different repo (instead of uninstalling and reinstalling Memcached).

    memcached_enablerepo: ""
    
The repository to use when installing Memcached (only used on RHEL/CentOS systems). If you'd like later versions of Memcached than are available in the OS's core repositories, use a repository like REMI (which can be installed with the geerlingguy.repo-remi).

## Dependencies

None.

## Example Playbook

    - hosts: cache
      roles:
        - { role: geerlingguy.memcached }

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
