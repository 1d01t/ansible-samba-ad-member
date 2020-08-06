# ansible-samba-ad-member


this ansible script installs Samba AD on debian buster, with:
  - bind9

Prepare plain debian buster instance
------------

  - install tasksel
  - add your ssh key to the instance
  - allow ssh root login
  - start ssh service

Modify the project to fit your needs
------------

smb.conf is configured to share a shared-directory for everyone in the domain.


Before you can use this project, you habe to set your configs in:
  - hosts
  - group_vars/homeserver/vars.yml
  - group_vars/homeserver/vault.yml

secure yourself and encrypt the vault.yml:
  - ansible-vault encrypt group_vars/homeserver/vault.yml

Build your own Samba-ad-member server
------------

finaly run:
  - ansible-playbook -i hosts sambamember.yaml --ask-vault-pass

