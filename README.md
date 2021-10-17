# knorrkator/ansible-etcd
Install Etcd with Docker on Raspberry Pis / Systems supporting ARM architecture

# Requires
- Please make sure that Docker is installed

# Install
Use following in your `requrements.yml`
```
roles:
  - name: knorrkator.ansible-etcd
    type: git
    version: 'main' # I actually would recommend to pin this to the commit id, to avoid pulling breaking changes
    source: git@github.com:knorrkator/ansible-etcd.git

```
An than run
```
ansible-galaxy install -r requirements.yml
```
- Optionally set `-p path/to/your/roles/dir` to specify a location where `ansible-galaxy` should put this role. E.g. `ansible-galaxy install -r requirements.yml -p roles/`

# Update
Get latest Git-Commit-ID or -Tag, update `version` in `requirements.yml` accordingly and run
```
ansible-galaxy install -r requirements.yml --force
```
> NOTE: this will update all your roles!


# Usage
```
- hosts: etcd
  gather_facts: False
  tasks:
    - include_role:
        name: knorrkator.ansible-etcd
```
