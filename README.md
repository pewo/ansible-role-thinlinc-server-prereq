# ansible-role-thinlinc-server-prereq
Prepare servers to be able to install ThinLinc using https://github.com/cendio/ansible-role-thinlinc-server.

Tested on containers:
 - centos-7-default
 - centos-8-default
 - debian-9.0-standard (stretch)
 - debian-10-standard (buster)
 - ubuntu-18.04-standard (bionic)
 - ubuntu-20.04-standard (focal)
 - ubuntu-20-10-standard (groovy) # WARNING, Installing old python2 packages
 - opensuse-15.2-default

Example playbook:

  ---
  - hosts: all
    gather_facts: false
  
    roles:
      - { role: ansible-role-thinlinc-server-prereq, install_xfce: true }
      - { role: ansible-role-thinlinc-server, thinlinc_accept_eula: "yes", thinlinc_server_bundle: "/local/artifactory/tl-4.12.1-server.zip" }
