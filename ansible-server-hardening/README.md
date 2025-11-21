# Automated Server Hardening & Docker Provisioning with Ansible 
This project is implementation of Infrastructure as Code (IAC) practices using Ansible to automate the server provisioning process from Fresh OS state to production ready.
The main focus of this project is security hardening and setting up containerization environment (Docker environment) without manual intervention.

# How do i run this project?

1. Make file configuration
2. Testing the code
3. Troubleshooting error problems
4. Understanding about the code 

- Following the command to run this project:
```bash
ansible-playbook main.yaml
```
note: make sure you place the user in the playbook directory not in the roles directory, Modify the `inventory` file and `ansible.cfg` according to your user on linux