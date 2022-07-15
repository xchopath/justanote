Ansible installation just `apt-get install ansible` with super-user.


### 1. Create a config

File: ~/.ansible.cfg
```
[defaults]
inventory = ~/.ansible/hosts

[inventory]
enable_plugins = yaml, ini
```


### 2. Create an inventory file

File: ~/.ansible/hosts
```
[hostgroup]
foo.domain.com ansible_port=22 ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa
192.168.12.34 ansible_port=22 ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa
```

### 3. Run a command

```
ansible foo.domain.com -a 'hostname'
```
