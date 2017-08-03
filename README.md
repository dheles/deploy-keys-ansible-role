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

    deploy_private_key:   "your_private_key"
    deploy_public_key:    "your_public_key"
    deploy_user:          "deploy"
    deploy_key_name:      "your_repo_deploy_key"
    deploy_key_full_path: "/home/{{ deploy_user }}/.ssh/{{ deploy_key_name }}"
    deploy_debugging:     "{{ debugging | default(false) }}"

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
