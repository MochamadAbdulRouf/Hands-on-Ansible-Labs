# Managing Roles Ansible
In this labs i learned how to manage roles, template, tasks, handlers.for specific /configurations and deep learn about it.

# How do i run this labs?

1. Create a specific configuration file like this .
2. Manage misconfigurations.
3. Run this playbook roles
- copy this command:
```bash
ansible-playbook site.yaml
```
- Maybe the log looks like this (do not copy this)
```bash
rouf@master-ansible:~/Hands-on-Ansible-Labs/managing-roles-v2$ ansible-playbook site.yaml 

PLAY [Deploy webserver nginx using role] ******************************************

TASK [Gathering Facts] ************************************************************
[WARNING]: Platform linux on host pod-ansible is using the discovered Python
interpreter at /usr/bin/python3.12, but future installation of another Python      
interpreter could change the meaning of that path. See
https://docs.ansible.com/ansible-
core/2.18/reference_appendices/interpreter_discovery.html for more information.    
ok: [pod-ansible]

TASK [my-nginx : install nginx] ***************************************************
ok: [pod-ansible]

TASK [my-nginx : start nginx service] *********************************************
ok: [pod-ansible]

TASK [my-nginx : Deploy index HTML page] ******************************************
changed: [pod-ansible]

RUNNING HANDLER [my-nginx : restart nginx] ****************************************
changed: [pod-ansible]

PLAY RECAP ************************************************************************
pod-ansible                : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

- note: If you do not detect any failures in the log, it means you have successfully implemented the Ansible role.
