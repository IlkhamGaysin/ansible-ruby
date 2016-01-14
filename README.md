RVM Ansible Role
=========

![HE:Labs](https://raw.githubusercontent.com/Helabs/helabs.github.com/master/images/logo.png "HE:Labs")

This is a simple role, based on [rvm/rvm1](https://github.com/rvm/rvm1-ansible)
that installs RVM and with this freshly installed RVM, installs any given ruby
packages.

Requirements
------------

This role only requires Ansible version 1.9+

Role Variables
--------------

All variables should be overwritten at the playbook level. Those are:

`gpg_key_server`: The gpg key server from which you will fetch the [RVM's creator's](https://keybase.io/mpapis)
public key:

    hkp://keys.gnupg.net

`gpg_key_id`: [Michal Papis'](https://keybase.io/mpapis) public keys:

    409B6B1796C275462A1703113804BB82D39DC0E3

`installer_url`: The url used by this role to fetch the RVM installer:

    https://get.rvm.io

`rvm_release`: The RVM release channel you want your host to be in:

    stable

`rvm_download_path`: Where to save the RVM installer:

    /tmp

`rvm_install_path`: The path where you want RVM to be installed on:

    /usr/local/rvm

`rvm_install_flags`: Additional flags that you would want to set on the RVM
install steps:

    --auto-dotfiles

`rvm_check_for_update`: Where or not you want to update RVM if it's already in
place:

    True

`rvm_autolib_mode`: [Autolibs](https://rvm.io/rvm/autolibs) is a feature built
into RVM to allow you to automatically install dependencies on your system.
These dependencies are typically things like OpenSSL, YAML and others.
You can also disable autolibs completely or do things in-between
"take care of it all" or "do nothing at all":

    3

`rvm_rubies`: List of ruby versions you want to install on this system:

    rvm_rubies:
      - ruby-2.2.2
      - ruby-2.1

`rvm_rubies_to_purge`: List of ruby versions (managed by RVM) you want to purge
from this system:

    rvm_rubies_to_purge:
      - ruby-2.1

`rvm_rubies_install_flags`: Additional flags that you would want to set on the
rubies install steps

`rvm_default_ruby_version`: The default ruby version to be used on this system.
This can also be overwritten, but it's not recomended since it defaults to
the latest ruby release listed on rvm:

    '{{ rvm_rubies | last if rvm_rubies and rvm_rubies is iterable else "" }}'

Dependencies
------------

This role has no dependecies

Using this role
----------------

Using this roles as as simples as:

    - hosts: servers
      become: yes
      become_user: app-local-non-root-user
      roles:
         - helabs.ruby

License
-------

BSD

Author Information
------------------

Lucas do Amaral Saboya Works as DevOps/SysOps @ [HE:Labs](https://www.helabs.com)
