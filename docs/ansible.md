# Ansible

## ansible-playbook

Example ansible-playbook command:
```bash
ansible-playbook --inventory-file hosts.txt --become --ask-become-pass --vault-password-file ~/.file.txt
```

## ansible-vault

Encrypt string into secret variable:
```bash
ansible-vault encrypt_string "bar" --name "foo"
```

Decrypt encrypted string in `vars/main.yml`:
```bash
ansible localhost -m debug -a 'var=certbot_EMAIL' -e "@vars/main.yml" --vault-password-file ~/.ANSIBLE_VAULT_PASSWORD
```