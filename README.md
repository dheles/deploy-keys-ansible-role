Ansible Role: Deploy Keys
=========

Configures a user with (pre-existing) deploy keys for a private git repo

Requirements
------------

An existing user
A (private) git repo, with the public deploy key configured
A keypair in the ansible project containing this role (preferably vault encrypted)

Role Variables
--------------

TBD

Dependencies
------------

None

Example Playbook

    - hosts: servers
      roles:
         - { role: deploy-keys }

License
-------

CC0

Author Information
------------------

Drew Heles
