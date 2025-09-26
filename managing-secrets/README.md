# MANAGING SECRETS USING ANSIBLE
* Apa itu managing secret di ansible? Managing secret bertujuan membuat pengguna baru diserver target dengan username dan password yang disimpan secara aman dan terenkripsi, bukan dalam bentuk teks biasa

1. Create directory
```bash
cd ~/
mkdir data-secret
cd data-secret
```

2. Create ansible configuration
```bash
vi ansible.cfg
```

3. Create inventory
```bash
vi inventory
```

4. Create secret file
```bash
vi secret.yaml
```

5. Encrypt files secret
```bash
ansible-vault encrypt secret.yaml
```
```bash
New Vault password: rouf
Confirm New Vault password: rouf
Encryption successful
```

6. Create Playbook
```bash
vi create-user.yaml
```

7. Run Playbook
```bash
ansible-playbook --syntax-check \
> --ask-vault-pass create_users.yml
echo 'rouf' > vault-pass
chmod 600 vault-pass
ansible-playbook \
> --vault-password-file=vault-pass create-users.yml
```