# MANAGING ROLES USING ANSIBLE
## Langkah pertama persiapan direktori dan konfigurasi awal

### Apa itu managing roles di ansible
* Managing roles di ansible bertujuan untuk mengubah serangkaian task yang panjang dan rumit menjadi satu yang sangat sederhana untuk di panggil

* Jika menggunakan cara manual bisa kita bayangkan menyiapkan webserver dari awal tanpa role, Kita harus menulis playbook yang panjang.

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

5. Create tasks to playbook
```bash
vi roles/myvhost/tasks/main.yaml
```

6. Create Handlers 
```bash
vi roles/myvhost/handlers/main.yaml
```

7. Create vhost-1 template
```bash
vi roles/myvhost/templates/vhost-1.conf.j2
```

8. Create vhost-2 template
```bash
vi roles/myvhost/templates/vhost-2.conf.j2
```

9. Create playbook
```bash
vi use-vhost-role.yaml
```

10. Running playbook
```bash
ansible-playbook use-vhost-role.yml \
> --syntax-check

ansible-playbook use-vhost-role.yml
```

