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

`gpg_key_server`: The gpg key server from which you will fetch the [RVM's creator's](https://keybase.io/mpapis)
public key:

    hkp://keys.gnupg.net

`rbenv_github_url`: The url from which we will fetch the rbenv's sources

    "https://github.com/rbenv/rbenv.git"

`rbenv_root`: The path where you want rbenv to be installed on

    "/usr/local/rbenv"

`rbenv_version`: The rbenv version you want to install

    "1.0.0"

`ruby_build_github_url`: The url from which we will fetch ruby-build's sources

    "https://github.com/rbenv/ruby-build.git"

`ruby_version`: The ruby version you want to install

    2.2.0

Dependencies
------------

This role has no dependecies

Using this role
----------------

Using this roles as as simples as:

    - hosts: servers
      become_user: app-local-non-root-user
      roles:
         - helabs.ruby

License
-------

BSD

Author Information
------------------

Lucas do Amaral Saboya Works as DevOps/SysOps @ [HE:Labs](https://www.helabs.com)
