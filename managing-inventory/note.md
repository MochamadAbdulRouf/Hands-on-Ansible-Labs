1. check list all hosts:

```bash
ansible all -i inventory --list-hosts
```

2. check list ungrouped hosts:

```bash
ansible ungrouped -i inventory --list-hosts
```

3. check host pod-ansible in the list of hosts in the inventory file

```bash
ansible pod-ansible -i inventory --list-hosts
```

4. check the list of hosts in the Development group.

```bash
ansible Development -i inventory --list-hosts
```

```bash
5. check the list host in the Indonesia group
ansible Indonesia -i inventory --list-hosts
```