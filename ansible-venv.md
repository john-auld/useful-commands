```
#!/bin/bash

#
# Example using Ansible installed in a virtualenv
#

TARGET=host.example.com
SSH_USER=centos
ENV=live
DEPLOY_USER=deploy

source /home/${DEPLOY_USER}/ansible/venv/bin/activate

/home/${DEPLOY_USER}/ansible/venv/bin/ansible-playbook \
    -i /home/${DEPLOY_USER}/${ENV}-hosts\
       /data/ansible/bootstrap-server/centos7-bootstrap.yml \
    --extra-vars " \
       	target=${TARGET} \
        ansible_ssh_user=${SSH_USER} \
    "
```


[Configure your ansible_python_interpreter](https://clouddocs.f5.com/products/orchestration/ansible/devel/usage/virtualenv.html)

When using Ansible in a virtualenv, it is necessary that you change your ansible_python_interpreter variable. This can be done in several places, including,

```
group_vars
host_vars
directly in the inventory file (on the hosts line)
```

The recommended place to put it though is in the group_vars directory in the all.yaml file. This will ensure that it is used by all of the hosts in your playbooks. Additionally, you can remove it from this central location if you move your playbooks to a non-virtualenv host.

Below is an example of what your inventory/group_vars/all.yaml file might look like after you have set the ansible_python_interpreter.

```
---
ansible_python_interpreter: /usr/local/bin/python
```

The same format would apply if you included it in your inventory/host_vars/HOST.yaml host files. To include it directly in inventory, the format looks a little different.

```
[f5-cli]
bigip5 ansible_host=1.2.3.4 ansible_python_interpreter=/opt/envs/my-venv/bin/python
```
