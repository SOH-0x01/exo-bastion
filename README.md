exo-bastion
=======

A set of Ansible playbooks to deploy a bastion instance on Exoscale.

A bastion host is a special purpose computer on a network specifically designed and configured to withstand attacks. In that case, it is meant to be the single point of access for ssh.

- [Exoscale](https://www.exoscale.ch/) is a Switzerland cloud provider for the digital native based on the Apache Cloudstack API.

- [Ansible](https://www.ansible.com/) is the simplest way to automate apps and infrastructure, the DevOps way.

**Note:** It provides only a basis to harden it yourself, please review the ssh, selinux and firewalling configuration to set the right level of security you want.


Getting Started
=======

First copy or create your cloudstack.ini with your exoscale credentials.

```
$ cat ./cloudstack.ini
[cloudstack]
endpoint = https://api.exoscale.ch/compute
key = cloudstack api key
secret = cloudstack api secret
method = post
```

Run the setup script to make sure the dependencies are met.
```
$ ./setup.sh
```

The script will do the following for you:
- Install or update Ansible, python module ansible
- Install or update your python cloudstack API, python module cs

Run the playbook to create the instance.
```
$ ansible-playbook create-instance.yaml
```

Feel free to adapt *group_vars/all.yaml* and *create-instance.yaml* to modify the parameters to your liking.


Authors
=======
Marc Guillen (marc.guillen@datsci.farm)

Licence
=======
GNU
Click on the [Link](COPYING) to see the full text.
