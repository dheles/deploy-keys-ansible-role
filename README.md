Ansible Role: Deploy Keys
=========

Configures a user with (pre-existing) deploy keys for private git repos

Requirements
------------

- An existing user
- One or more (private) git repos, with the public deploy keys configured
- One or more keypairs in the ansible project containing this role (preferably vault encrypted)

Role Variables
--------------

    deploy_user:      "deploy"
    deploy_debugging: "{{ debugging | default(false) }}"
    deploy_key_path:  "/home/{{ deploy_user }}/.ssh"
    deploy_keys:
      - name:         "your_first_repo_deploy_key_name"
        private_key:  "your_first_private_key"
        public_key:   "your_first_public_key"

  optionally, for additional keys on the same server:
  
      - name:         "your_second_repo_deploy_key_name"
        private_key:  "your_second_private_key"
        public_key:   "your_second_public_key"

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: deploy-keys }

if you have sets of keys stored for different servers, you can re-use the role like so:

    - hosts: application
      roles:
         - { role: deploy-keys,  deploy_keys: "{{ app_deploy_keys }}" }

     - hosts: solr
       roles:
          - { role: deploy-keys,  deploy_keys: "{{ solr_deploy_keys }}" }

License
-------

CC0

Author Information
------------------

Drew Heles
