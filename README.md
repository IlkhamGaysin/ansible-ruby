RBenv Ansible Role
=========

![HE:Labs](https://raw.githubusercontent.com/Helabs/helabs.github.com/master/images/logo.png "HE:Labs")

This is a simple role, based on [rbenv](https://github.com/rbenv/rbenv)
that installs rbenv and with this freshly installed rbenv, installs any given
ruby packages.

Requirements
------------

This role only requires Ansible version 1.9+

Role Variables
--------------

All variables should be overwritten at the playbook level. Those are:

`rbenv.env`: Type of rbenv installation. Allows 'system' or 'user' values
`rbenv.version`: Version of rbenv to install (tag from rbenv releases page)
`rbenv.ruby_version`: Version of ruby to install as global rbenv ruby
`rbenv_repo`: Repository with source code of rbenv to install
`rbenv_plugins`: Array of Hashes with information about plugins to install
`rbenv_root`: rbenv install path
`rbenv_users`: array of usernames for multiuser install. User must be present in
the system

Dependencies
------------

This role has no dependecies

Using this role
----------------

Using this roles as as simples as:

    - hosts: servers
      gather_facts: true
      vars:
        rbenv:
          env: user
          version: v0.4.0
          ruby_version: 2.0.0-p353
      roles:
         - helabs.ruby
           rbenv_users:
            - app_user

License
-------

BSD

Author Information
------------------

Lucas do Amaral Saboya Works as DevOps/SysOps @ [HE:Labs](https://www.helabs.com)
