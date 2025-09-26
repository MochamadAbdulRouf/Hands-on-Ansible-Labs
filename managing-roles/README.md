# MANAGING ROLES USING ANSIBLE
## Langkah pertama persiapan direktori dan konfigurasi awal

1. Create directory
```bash
cd ~/
mkdir role-create
cd role-create
```

2. Create Ansible Configuration
```bash
vi ansible.cfg
```

3. Create inventory
```bash
vi inventory
```

4. Create roles
```bash
mkdir roles
cd roles
ansible-galaxy init myvhost
```
```bash
rm -rvf myvhost/{defaults,vars,tests}
cd ..
```
```bash
mkdir -p roles/myvhost/files/html-1

mkdir -p roles/myvhost/files/html-2

echo 'simple index vhost1 : pod-username' > \
> roles/myvhost/files/html-1/index.html

echo 'simple index vhost2 : pod-username' > \
> roles/myvhost/files/html-2/index.html
```


