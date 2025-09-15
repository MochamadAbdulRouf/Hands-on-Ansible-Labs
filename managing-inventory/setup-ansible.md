Create and Distribute SSH Keygen
Execute on all nodes

1. Create a ssh-keygen so you can ssh without a password
```bash
student@pod-username-controller:~$ ssh-keygen
student@pod-username-managed1:~$ ssh-keygen
student@pod-username-managed2:~$ ssh-keygen
```

2. Copy all public key from regular user to all nodes
```bash
student@pod-username-controller:~$ ssh-copy-id student@pod-username-controller
student@pod-username-controller:~$ ssh-copy-id student@pod-username-managed1
student@pod-username-controller:~$ ssh-copy-id student@pod-username-managed2
...
student@pod-username-managed1:~$ ssh-copy-id student@pod-username-controller
student@pod-username-managed1:~$ ssh-copy-id student@pod-username-managed1
student@pod-username-managed1:~$ ssh-copy-id student@pod-username-managed2
...
student@pod-username-managed2:~$ ssh-copy-id student@pod-username-controller
student@pod-username-managed2:~$ ssh-copy-id student@pod-username-managed1
student@pod-username-managed2:~$ ssh-copy-id student@pod-username-managed2
```

3. Check if the host can access without using a password (passwordless).
```bash
student@pod-username-controller:~$ ssh student@pod-username-controller "whoami; hostname"
student@pod-username-controller:~$ ssh student@pod-username-managed1 "whoami; hostname"
student@pod-username-controller:~$ ssh student@pod-username-managed2 "whoami; hostname"
...
student@pod-username-managed1:~$ ssh student@pod-username-controller "whoami; hostname"
student@pod-username-managed1:~$ ssh student@pod-username-managed1 "whoami; hostname"
student@pod-username-managed1:~$ ssh student@pod-username-managed2 "whoami; hostname"
...
student@pod-username-managed2:~$ ssh student@pod-username-controller "whoami; hostname"
student@pod-username-managed2:~$ ssh student@pod-username-managed1 "whoami; hostname"
student@pod-username-managed2:~$ ssh student@pod-username-managed2 "whoami; hostname"
```

4. Create swap file. Only executed in the controller

#creating a file which will be used for swap:
```bash
sudo fallocate -l 2G /swapfile
```
#Only the root user should be able to write and read the swap file. Set the correct permissions by typing:
```bash
sudo chmod 600 /swapfile
```

#Use the mkswap utility to set up a Linux swap area on the file:
```bash
sudo mkswap /swapfile
```

#Activate the swap file using the following command:
```bash
sudo swapon /swapfile
```

#To make the change permanent open the /etc/fstab file. add to new line don't change anything already exist:
#sudo vim /etc/fstab
#and paste the following line:
...
/swapfile swap swap defaults 0 0
...
#verify
```bash
sudo swapon --show
```
Configuring nusactl requirements
Execute this config only in pod-username-controller


2. automate ssh-add automatically when logged in
```bash
sudo apt install -y keychain && echo "eval $(keychain -q --eval id_rsa)" >> .bashrc && source .bashrc
```
3. Setup default configuration ansible.
```bash
student@pod-[username]-controller:~$ sudo mkdir -p /etc/ansible
student@pod-[username]-controller:~$ sudo vim /etc/ansible/hosts
pod-[username]-managed1

[webservers]
pod-[username]-managed2
```

4. Show all hosts from inventory.
```bash
student@pod-[username]-controller:~$ ansible all --list-hosts

5. Show ungrouped hosts from inventory.
```bash
student@pod-[username]-controller:~$ ansible ungrouped --list-hosts
```
6. Show hosts in group webservers.
```bash
student@pod-[username]-controller:~$ ansible webservers --list-hosts
```
7. Check ping to all node.
```bash
student@pod-[username]-controller:~$ ansible all -m ping
```

### Source by Ansible Documentation and Adinusa