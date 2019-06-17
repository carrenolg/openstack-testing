# Ansible playbook - creating openstack resources


## Setting the project

clouds.yaml is a configuration file that contains everything needed to connect to one or more clouds. It may contain private information and is generally considered private to a user.

OpenStackClient looks for a file called clouds.yaml in the following locations:

- current directory
- ~/.config/openstack
- /etc/openstack

It is advisable putting the clouds.yml file in the `~/.config/openstack` location.

Example:
```
clouds:
  ormuco:
    auth:
      auth_url: https://api.example.com:5000/v3
      username: {your_user}
      password: {your_password}
      tenant_id: {projectID}
    region_name: {region}
    identity_api_version: 3
```
In the above example, there is a cloud called "ormuco". This name will be reference from playbook in the `site.yml`

```
- hosts: localhost
  remote_user: root
  roles:
    - ormuco
```

## Run the playbook

1. Clone the repository
```
$ git clone https://github.com/carrenolg/openstack-testing.git
```

2. Dowload image and save it in the root directory
```
$ wget http://download.cirros-cloud.net/
```

3. Put your the sshkey path in the `roles/ormuco/vars/main.yml`

```
---
# vars file for ormuco
path_ssh_key: "your_ssh_key_path"
```

4. Run playbook 

```
$ ansible-playbook site.yml
```

